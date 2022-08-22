# Providers

* São utilizados para criar services, factories, helpers, etc.;
* O decorator @Injectable() é utilizado para criar uma classe provider;
* Podem ser injetados dentro de controllers e outros providers, usando a injeção de dependência embarcada no Nest;
* Podem ser exportados por um module, se tornando disponíveis para um outro module importa-los.
