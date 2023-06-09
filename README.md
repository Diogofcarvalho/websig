# README

Este código HTML foi utilizado para a criação de um mapa sobre os casos de Covid-19 para o dia 23 de Janeiro

## Estrutura do Código

O código HTML está estruturado da seguinte maneira:

- Na parte `<head>`, estão todas  as bibliotecas utilizadas e estilos necessários para a criação do mapa.

- A seção `<body>` contém a estrutura da página, incluindo a div onde o mapa será exibido.

- No final do arquivo, há um `<script>` que contém o código JavaScript responsável por configurar o mapa e suas funcionalidades.

## Configurações do mapa

- `L.map('map').setView([38.749, -9.155], 13)`: Inicia o mapa, definie a localização e o nível de zoom que pretendemos.

- `L.tileLayer`: Adiciona uma camada  do OpenStreetMap ao mapa.

- `L.tileLayer.wms`: Adiciona uma camada WMS do Geoserver ao mapa, para este caso foi utilizada a shapefile dos concelhos

## Estilos e Cores

- `getcor10k(d)`: Função que atribui uma cor com base no número de casos de Covid-19 por 10.000 habitantes.

- `estilo10k(feature)`: Define o estilo dos polígonos no mapa com base nos dados de casos de Covid-19 por 10.000 habitantes.

## Camadas de Dados

- `L.geoJSON(casos10kData)`: Cria uma camada de polígonos no mapa usando dados GeoJSON de casos de Covid-19 por 10.000 habitantes.

- `L.markerClusterGroup()`: Cria um grupo de clusters de marcadores para agrupar os marcadores relacionados aos casos de Covid-19, criando pontos com o número de casos que se agrupam.

## Controles e Legenda

- `L.control.scale()`: Adiciona uma escala ao mapa.

- `L.control.layers`: Possibilita escolher a camada que pretendemos visualizar.

- `L.control({ position: 'bottomright' })`: Cria uma legenda na parte inferior direita do mapa.



