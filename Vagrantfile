Vagrant.configure("2") do |config|
  # Define o sistema operacional base (Ubuntu 20.04)
  config.vm.box = "ubuntu/focal64"
  
  # Redireciona a porta 80 da máquina virtual para a 8080 do seu computador host
  config.vm.network "forwarded_port", guest: 80, host: 8080

  # Seção de provisionamento com Shell Script inline
  config.vm.provision "shell", inline: <<-SHELL
    echo "Atualizando os pacotes..."
    sudo apt-get update
    
    echo "Instalando o servidor Apache..."
    sudo apt-get install -y apache2
    
    echo "Garantindo que o Apache inicie automaticamente..."
    sudo systemctl start apache2
    sudo systemctl enable apache2
  SHELL
end