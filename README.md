# Roteamento  resiliente 

### Pastas

- build
    - docker-compose.build.yml
        
        Esse arquivo é rodado uma unica vez. Justamente para carregar todos os tiles e configurações iniciais do valhalla.
        
        Para rodar use `docker-compose -f docker-compose.build.yml up`
        
- runtime
    - docker-compose.yml
        
        Esse arquivo é rodado para iniciar o container do valhalla. Rodando toda vez que queremos iniciar o container.
        
        Para rodar use `docker-compose up`
        
- data
    Deve-se criar essa pasta 'data' na raiz do projeto contendo o arquivo OpenStreetMap (.pbf). Nesse projeto foi utilizado o `sudeste-latest.osm.pbf`
    
    - sudeste-latest.osm.pbf
        
        Esse arquivo é a malha da localidade que queremos utilizar o valhalla. Sendo representada somente pela região sudeste nesse projeto. Após rodar o build deverá criar automaticamente as pastas tiles, valhalla e valhalla.json
        
        Para baixar demais localidades, visite: [https://download.geofabrik.de/](https://download.geofabrik.de/south-america/brazil.html) 
        
        > Sempre que baixar uma nova localidade, Rode o build novamente com a região desejada dentro da pasta ‘data’ e aponte devidamente no arquivo `docker-compose.build.yml`
        >