# FIWARE-LD (mobile client)

Este aplicativo coleta dados do dispositivo móvel e os envia para um servidor FIWARE-LD, utilizando a API NGSI-LD. O objetivo é integrar os dados do dispositivo, como geolocalização e sensores, em um ambiente inteligente que pode ser consumido por sistemas FIWARE-LD.

### Dados Coletados

O aplicativo coleta as seguintes informações do dispositivo:

#### 1. **Dispositivo**
- **Host**: Nome do host.
- **Marca**: Marca do dispositivo.
- **Modelo**: Modelo do dispositivo.
- **Versão do Android**: Versão do sistema operacional Android.
- **Data/Hora**: Data e hora atual.

#### 2. **Geolocalização**
- **Latitude**: Latitude atual do dispositivo.
- **Longitude**: Longitude atual do dispositivo.

#### 3. **Sensores**
- **Acelerômetro**: Dados de aceleração em diferentes eixos (X, Y, Z).
- **Giroscópio**: Dados de rotação do dispositivo.
- **Barômetro**: Pressão atmosférica detectada.
- **Magnetômetro**: Dados magnéticos para orientação do dispositivo.
- **Temperatura**: Temperatura do ambiente.
- **Umidade**: Nível de umidade do ambiente.
- **Luz ambiente**: Intensidade da luz ambiente.
- **Ruído**: Medição do nível de ruído ambiente.

#### 4. **Pedômetro**
- **Passos**: Contagem de passos do usuário.

## Bibliotecas Utilizadas

O aplicativo utiliza as seguintes bibliotecas para coletar dados e interagir com o sistema:

- **[device_info_plus](https://pub.dev/packages/device_info_plus)** (Versão: ^11.2.2)
  - Coleta dados sobre o dispositivo, como marca, modelo e versão do Android.

- **[environment_sensors](https://pub.dev/packages/environment_sensors)** (Versão: ^0.3.0)
  - Acessa sensores como temperatura e umidade do ambiente.

- **[http](https://pub.dev/packages/http)** (Versão: ^1.3.0)
  - Realiza requisições HTTP para enviar os dados para o servidor.

- **[light](https://pub.dev/packages/light)** (Versão: ^4.0.0)
  - Acessa o sensor de luz ambiente.

- **[location](https://pub.dev/packages/location)** (Versão: ^5.0.2)
  - Obtém dados de geolocalização do dispositivo (latitude e longitude).

- **[noise_meter](https://pub.dev/packages/noise_meter)** (Versão: ^5.0.2)
  - Mede o nível de ruído ambiente.

- **[pedometer](https://pub.dev/packages/pedometer)** (Versão: ^4.0.2)
  - Conta os passos do usuário.

- **[permission_handler](https://pub.dev/packages/permission_handler)** (Versão: ^11.3.1)
  - Gerencia as permissões necessárias para acessar sensores e localização.

- **[sensors_plus](https://pub.dev/packages/sensors_plus)** (Versão: ^6.1.1)
  - Acessa os sensores de movimento, como acelerômetro, giroscópio, barômetro e magnetômetro.

- **[shared_preferences](https://pub.dev/packages/shared_preferences)** (Versão: ^2.5.1)
  - Armazena configurações e preferências do usuário.

- **[telephony_info_plus](https://pub.dev/packages/telephony_info_plus)** (Versão: ^0.0.2)
  - Obtém informações sobre o chip do celular, como provedor e intensidade do sinal.

## Envio de Dados

Os dados coletados são enviados para o servidor **Orion-LD**, um broker de contexto do FIWARE-LD, via APIs NGSI-LD. O envio é realizado usando a biblioteca **[http](https://pub.dev/packages/http)**.

A estrutura das requisições NGSI-LD segue os exemplos fornecidos pelo **Postman da FIWARE-LD**, garantindo a compatibilidade com o sistema FIWARE-LD.

## Interface do Usuário

O aplicativo possui uma interface simples, com as seguintes telas:

1. **Tela de Configuração de Servidor**: Permite que o usuário informe o endereço do servidor FIWARE-LD.
2. **Tela de Detalhes**: Exibe informações em tempo real sobre o dispositivo, sensores e localização.
3. **Tela de Configuração de Exibição**: Permite que o usuário configure os dados que serão exibidos em tela e enviados para o servidor FIWARE-LD.

Ao iniciar o aplicativo pela primeira vez, um breve tutorial de uso será exibido automaticamente. Você também pode acessá-lo posteriormente na seção "Instruções de Uso" deste arquivo.


## Tecnologias Utilizadas

O aplicativo foi desenvolvido com as seguintes tecnologias:

- **Flutter**: Framework utilizado para o desenvolvimento cross-platform (versão 3.27.3).
- **Dart**: Linguagem de programação utilizada (versão 3.6.1).
- **NGSI-LD**: Padrão utilizado para a comunicação com o FIWARE-LD.
- **Android SDK**: Versão 35 da plataforma Android.
- **JDK**: Java Development Kit versão 17.0.12.
- **Android Studio**: IDE utilizada (versão 2024.2.2.13 - LadyBug).

## Dispositivos Compatíveis

O aplicativo foi testado e é compatível com os seguintes dispositivos:

- **Samsung**
- **Motorola**
- **Xiaomi**

## Instruções de Uso

1. **Instalar o aplicativo** no dispositivo Android via APK.
2. **Informar servidor FIWARE**: O aplicativo solicitará o endereço do servidor para continuar.
3. **Conceder permissões**: Para que o aplicativo funcione corretamente, conceda as permissões para acessar localização, atividade física, microfone e dados do telefone.
4. **Verificar dados**: Acompanhe a coleta de dados em tempo real através da tela principal.
5. **Enviar dados**: O aplicativo automaticamente envia os dados coletados para o servidor FIWARE-LD via API NGSI-LD.
