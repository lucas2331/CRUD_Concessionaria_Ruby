# CRUD Concessionaria | Ruby

```ruby

Verificador = true
ListaTotal = []

while Verificador == true

  STDOUT.flush
  puts "\n[X]Olá, bem vindo ao Crud de Concessionaria!"
  puts "[1]Cadastrar."
  puts "[2]Apresentar."
  puts "[3]Alterar."
  puts "[4]Excluir."
  puts "[5]Sair."
  puts "[X]Escolha uma opção: "
  Opção = gets.chomp

  if Opção == '1'
    puts "\n[X]Opção de Cadastrar"

    puts "\n[X]Digite o codigo do carro: "
    Codigo = gets.chomp

    puts "\n[X]Digite o nome do carro: "
    Nome = gets.chomp
    
    puts "\n[X]Digite o ano do carro: "
    Ano = gets.chomp
  
    puts "\n[X]Digite o tipo de combustivel do carro: "
    Combustivel = gets.chomp
    
    puts "\n[X]Digite a configuração do carro: "
    Configuração = gets.chomp
    
    puts "\n[X]Digite a quantidade de lugares do carro: "
    Lugares = gets.chomp
    
    puts "\n[X]Digite o tipo de tração do carro: "
    Tração = gets.chomp

    DadosCompleto = Codigo + " | " + Nome + " | " + Ano + " | " + Combustivel + " | " + Configuração + " | " + Lugares + " | " + Tração
    ListaTotal.push(DadosCompleto)

  elsif Opção == '2'
    puts "\n[X]Opção de Apresentar"

    TamanhoLista = ListaTotal.length()

    if TamanhoLista == 0
      puts "[X]Nenhum usuário registrado!"
    else
      puts ListaTotal
    end

  elsif Opção == '3'
    puts "\n[X]Opção de Alterar"

    TamanhoListaAltera = ListaTotal.length()

    if TamanhoListaAltera == 0
      puts "[X]Nenhum usuário registrado!"
    
    else   
      puts "\n[X]Digite o carro a ser alterado: "
      CarroAlterar = gets.chomp

      Verificador = 0

      ListaTotal.each_with_index do |shark, index|
        
        if CarroAlterar == index.to_s
          Verificador = Verificador + 1
        else
          Verificador = Verificador + 0
        end

      end

      if Verificador > 0

        puts "\n[X]Digite o codigo do carro: "
        CodigoAltera = gets.chomp

        puts "\n[X]Digite o nome do carro: "
        NomeAltera = gets.chomp
    
        puts "\n[X]Digite o ano do carro: "
        AnoAltera = gets.chomp
  
        puts "\n[X]Digite o tipo de combustivel do carro: "
        CombustivelAltera = gets.chomp
    
        puts "\n[X]Digite a configuração do carro: "
        ConfiguraçãoAltera = gets.chomp
    
        puts "\n[X]Digite a quantidade de lugares do carro: "
        LugaresAltera = gets.chomp
    
        puts "\n[X]Digite o tipo de tração do carro: "
        TraçãoAltera = gets.chomp

        DadosCompletoAltera = CodigoAltera + " | " + NomeAltera + " | " + AnoAltera + " | " + CombustivelAltera + " | " + ConfiguraçãoAltera + " | " + LugaresAltera + " | " + TraçãoAltera

        ListaTotal[CarroAlterar.to_i] = DadosCompletoAltera.to_s

      else
        puts "[X]Carro inexistente"
      end
    end

  elsif Opção == '4'
    puts "\n[X]Opção de Excluir"

    TamanhoLista = ListaTotal.length()

    if TamanhoLista == 0
      puts "[X]Nenhum usuário registrado!"
    else
      
      puts "\n[X]Digite o carro a ser excluido: "
      CarroExclui = gets.chomp

      Verificador = 0

      ListaTotal.each_with_index do |shark, index|
        
        if CarroExclui == index.to_s
          Verificador = Verificador + 1
        else
          Verificador = Verificador + 0
        end

      end

      if Verificador > 0
        ListaTotal.delete_at(CarroExclui.to_i)
      else
        puts "[X]Carro inexistente"
      end
    end

  elsif Opção == '5'
    puts "\n[X]Opção de Sair. Obrigado!"
    exit


  else
    puts "\n[X]Escolha uma opção válida!"
  end  
end

```
