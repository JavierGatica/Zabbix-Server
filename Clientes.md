# Configuración de clientes.

Para el siguiente ejercio utilizaremos 6 equipos los cuales son los siguientes:
* agent01.ansible-labs.com
* agent02.ansible-labs.com
* agent03.ansible-labs.com
* agent04.ansible-labs.com
* agent05.ansible-labs.com
* agent06.ansible-labs.com

Los cuales cuentan con las siguientes caracteristicas:
* **SO:** RHEL 7.8 - Minimal.
* **RMA:** 1 GB.
* **HDD:** 6 GB.
* **Vcpu:** 1.

Estos equipos se encuentran registrado a un servidor RH-Satellite que proporciona los paquetes necesarios para actualizaciones y remediaciones.

## Proceso de registro.

Descarcar el certificado de katello a los clientes.

    [root@agent01 ~]# curl --insecure --output katello-ca-consumer-latest.noarch.rpm https://satellite-infra.ansible-labs.com/pub/katello-ca-consumer-latest.noarch.rpm
    
Instalar el certificado.

    [root@agent01 ~]# yum localinstall katello-ca-consumer-latest.noarch.rpm  -y
    Complementos cargados:product-id, search-disabled-repos, subscription-manager

    This system is not registered with an entitlement server. You can use subscription-manager to register.

    Examinando katello-ca-consumer-latest.noarch.rpm: katello-ca-consumer-satellite-infra.ansible-labs.com-1.0-1.noarch
    Marcando katello-ca-consumer-latest.noarch.rpm para ser instalado
    Resolviendo dependencias
    --> Ejecutando prueba de transacción
    ---> Paquete katello-ca-consumer-satellite-infra.ansible-labs.com.noarch 0:1.0-1 debe ser instalado
    --> Resolución de dependencias finalizada

    Dependencias resueltas

    =====================================================================================================================================================================================================================
     Package                                                                        Arquitectura                     Versión                          Repositorio                                                  Tamaño
    =====================================================================================================================================================================================================================
    Instalando:
     katello-ca-consumer-satellite-infra.ansible-labs.com                           noarch                           1.0-1                            /katello-ca-consumer-latest.noarch                            16 k

    Resumen de la transacción
    =====================================================================================================================================================================================================================
    Instalar  1 Paquete

    Tamaño total: 16 k
    Tamaño instalado: 16 k
    Downloading packages:
    Running transaction check
    Running transaction test
    Transaction test succeeded
    Running transaction
      Instalando    : katello-ca-consumer-satellite-infra.ansible-labs.com-1.0-1.noarch                                                                                                                              1/1 
      Comprobando   : katello-ca-consumer-satellite-infra.ansible-labs.com-1.0-1.noarch                                                                                                                              1/1 

    Instalado:
      katello-ca-consumer-satellite-infra.ansible-labs.com.noarch 0:1.0-1      
