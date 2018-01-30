# Orquestación de máquinas virtuales

## Ejercicio 1

Instalar una máquina virtual Debian usando Vagrant y conectar con ella.

Con el siguiente vagrant file podremos crear una máquina Debian en azure:

    Vagrant.configure('2') do |config|
        config.vm.box = 'azure'

        # Path a tu clave ssh
        config.ssh.private_key_path = '~/.ssh/id_rsa'

        config.vm.define "api" do |api|
            api.vm.provider :azure do |azure, override|

                # Establece la localización de la máquina virtual
                azure.location = "eastus"

                # Nombre del grupo de recursos y de la máquina a crear
                azure.resource_group_name = "CC"
                azure.vm_name = "cloudcomputingapi"

                # Tipo de máquina a desplegar
                azure.vm_size = "Standard_DS1_v2"

                # Imagen a instalar en la máquina
                azure.vm_image_urn = "credativ:Debian:8:latest"

                # Subscripción de azure
                azure.subscription_id = ENV['AZURE_SUBSCRIPTION_ID']

                # Detalles de la cuenta de azure
                azure.tenant_id = ENV['AZURE_TENANT_ID']
                azure.client_id = ENV['AZURE_CLIENT_ID']
                azure.client_secret = ENV['AZURE_CLIENT_SECRET']

            end  
        end  

        config.vm.provision "ansible" do |ansible|  
            ansible.playbook = "provision.yml"  
        end  

    end


## Ejercicio 3

Crear un script para provisionar de forma básica una máquina
virtual para el proyecto que se esté llevando a cabo en la asignatura.

Con el siguiente Vagrantfile se provisona de forma simple la máquina creada:

    Vagrant.configure('2') do |config|
        config.vm.box = 'azure'

        config.vm.provision "shell"
          inline:"apt-get install python2.7 python-pip"
          inline:"pip install flask flask-restful flask-jsonpify pymongo"

    end


## Ejercicio 4

Configurar tu máquina virtual usando `vagrant` con el provisionador
ansible.

En el mismo directorio que nuestro script de ansible, creamos el siguiente **Vagrantfile:**

    Vagrant.configure('2') do |config|
        config.vm.box = 'azure'

        # Path a tu clave ssh
        config.ssh.private_key_path = '~/.ssh/id_rsa'

        config.vm.define "api" do |api|
            api.vm.provider :azure do |azure, override|

                # Establece la localización de la máquina virtual
                azure.location = "eastus"

                # Nombre del grupo de recursos y de la máquina a crear
                azure.resource_group_name = "CC"
                azure.vm_name = "cloudcomputingapi"

                # Tipo de máquina a desplegar
                azure.vm_size = "Standard_DS1_v2"

                # Imagen a instalar en la máquina
                azure.vm_image_urn = "credativ:Debian:8:latest"

                # Subscripción de azure
                azure.subscription_id = ENV['AZURE_SUBSCRIPTION_ID']

                # Detalles de la cuenta de azure
                azure.tenant_id = ENV['AZURE_TENANT_ID']
                azure.client_id = ENV['AZURE_CLIENT_ID']
                azure.client_secret = ENV['AZURE_CLIENT_SECRET']

            end  
        end  

        config.vm.provision "ansible" do |ansible|  
            ansible.playbook = "provision.yml"  
        end  

    end
