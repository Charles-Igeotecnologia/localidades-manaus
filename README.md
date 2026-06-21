# Web GIS Manaus — Localidades, Bairros e Zonas

Aplicação Web GIS interativa e responsiva voltada para a visualização, análise cartográfica e geração de relatórios das divisões administrativas (Bairros e Zonas) e subdivisões informais/oficiais (Localidades como conjuntos, condomínios, residenciais e comunidades) do município de Manaus, Amazonas.

Construído utilizando **Leaflet.js**, **Tailwind CSS** e **Lucide Icons** para entregar uma interface moderna, rápida e no tema escuro premium.

## 🚀 Funcionalidades

1. **Navegação Cartográfica Avançada**:
   * Alternância entre mapas base: Vetor (OSM), Imagem de Satélite (Esri), Satélite Híbrido (Google Maps com logradouros sobrepostos) e Tema Escuro (CartoDB).
   * Rótulos permanentes dos bairros com **Halo Cartográfico** (contorno preto de alto contraste) que garante leitura ideal sobre o satélite.
   * Destaques visuais e tooltips (*rótulos flutuantes*) ao passar o mouse pelas feições.

2. **Geração de Relatório Técnico (Preview A4)**:
   * Painel de visualização prévia da folha no formato A4 em tempo real.
   * Sincronização inteligente de mapas: o mapa do relatório herda a posição e o basemap do mapa de fundo.
   * Tabela dinâmica com informações da feição (bairro/localidade) selecionada.
   * Legendas geradas automaticamente baseadas apenas nas camadas ativas no recorte.
   * Campo de notas/observações editáveis antes da geração final.
   * Exportação sem cortes ou deslocamentos para impressora ou arquivo **PDF**.

3. **Interações Espaciais**:
   * Ferramenta de medição para desenhar linhas/polígonos e calcular perímetros e áreas (em metros e hectares).
   * Sistema de cálculo de proximidade: cliques livres no mapa calculam e listam os 3 pontos de referência mais próximos em um raio de até 1 km (Haversine).
   * Integração de link direto das coordenadas centroides com o Google Maps.
   * Barra de busca rápida com autocomplete para encontrar bairros, condomínios, conjuntos e comunidades com zoom suave (*flyTo*).

## 🛠️ Como Executar Localmente

Como a aplicação é estática pura, você pode rodá-la simplesmente servindo os arquivos locais. Por exemplo, utilizando Node.js (`http-server`):

```bash
# Instalar e rodar o servidor na porta 8085
npx http-server -p 8085
```

Em seguida, acesse no seu navegador:
[http://localhost:8085](http://localhost:8085)

## 📂 Estrutura de Arquivos do Projeto

* `index.html`: Código-fonte principal da aplicação (estrutura, estilos e lógica JS).
* `bairros_data.js` & `localidades_data.js`: Banco de dados espaciais compilado em escopo global Javascript (GeoJSON).
* `bairros.geojson` & `localidades.geojson`: Arquivos vetoriais GeoJSON originais.
* `BAIRROS E ZONAS MANAUS.gpkg` & `LOCALIDADES MANAUS.gpkg`: Pacotes de dados espaciais no formato GeoPackage para uso em softwares GIS (QGIS, ArcGIS).
