# README

Este código HTML foi utilizado para a criação de um mapa sobre os casos de Covid-19 para o dia 23 de Janeiro

## Estrutura do Código

O código HTML está estruturado da seguinte forma:

- Na parte `<head>`, estão todas  as bibliotecas utilizadas e estilos necessários para a criação do mapa.

- A seção `<body>` contém a estrutura da página, incluindo a div onde o mapa será exibido.

- No final do arquivo, há um `<script>` que contém o código JavaScript responsável por configurar o mapa.

## Configurações do mapa

- `L.map('map').setView([38.749, -9.155], 13)`: Inicia o mapa, definie a localização e o nível de zoom que pretendemos.

- `L.tileLayer`: Adiciona uma layer  do OpenStreetMap ao mapa.

- `L.tileLayer.wms`: Adiciona uma layer WMS do Geoserver ao mapa, para este caso foi utilizada a shapefile dos concelhos

## Estilos e Cores

- `getcor10k(d)`: Função que atribui uma cor com base no número de casos de Covid-19 por 10.000 habitantes.

- `estilo10k(feature)`: Define o estilo dos polígonos no mapa com base nos dados de casos de Covid-19 por 10.000 habitantes.

## Layers

- `L.geoJSON(casos10kData)`: Cria uma layer do tipo polígonos no mapa usando dados GeoJSON de casos de Covid-19 por 10.000 habitantes.

- `L.markerClusterGroup()`: Cria um grupo de clusters de marcadores para agrupar os marcadores relacionados aos casos de Covid-19, criando pontos com o número de casos que se agrupam.

## Controlos e Legenda

- `L.control.scale()`: Adiciona uma escala ao mapa.

- `L.control.layers`: Possibilita escolher a camada que pretendemos visualizar.

- `L.control({ position: 'bottomright' })`: Cria uma legenda na parte inferior direita do mapa.


## O mapa contém as seguintes funções
- Iniciação do mapa: O mapa é inicializado usando o Leaflet e definido para ser exibido na caixa com o ID "map".
- Carregar as layers base: A layer do OpenStreetMap é carregada e adicionada ao mapa.
- Layer dos concelhos (CONCELHOS): Uma layer com os concelhos é carregada a partir de um servidor WMS, que vai buscar informação ao GeoServer e adicionada ao mapa.
- Funções para estilo e interação com a layer de casos por 10 mil habitantes: As funções são definidas para criar um estilo e um conjunto de ações com a layer de casos por 10 mil habitantes sendo que estas funções determinam a cor dos polígonos com base no número de casos e definem ações como destacar o polígono ao passar por cima com o rato.
- Criação da layer de casos por 10 mil habitantes: A layer de casos por 10 mil habitantes é criada a partir de dados GeoJSON onde também é definido um estilo e um conjunto de ações usando as funções definidas anteriormente. A camada é adicionada ao mapa.
- Criação de marcadores de casos: Marcadores de casos individuais são criados a partir de dados GeoJSON e agrupados usando a extensão Leaflet.MarkerCluster. Os marcadores são adicionados ao mapa.
- Criação da legenda: Uma legenda é criada e pode ser visualizada no canto inferior direito do mapa.
- Controlos da layer: Controlos de layer são criados para alternar entre a layer base e a de sobreposição.
- Controlo de informações: Um controlo de informações é criado para exibir informações sobre o concelho selecionado.
- Funções para destaque e zoom: Funções definidas para destacar polígonos ao passar o rato por cima e ajustar.


