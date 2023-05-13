# Final_Project_MBA_DSA

## 1) Trabalhando os dados de acidentes

### Encontrar endereço 

Foi preciso encontrar o endereço da ocorrência de cada acidente a partir das suas coordenadas.
Biblioteca utilizada:Geopy.

#### Instalação
```
$ pip install geopy
```

#### Importando dados 

```python
  import pandas as pd
  df = pd.read_excel('Coordenadas.xlsx')

  from geopy.geocoders import Nominatim
  geolocator = Nominatim(user_agent="meu_endereço")
  
  # Como eram muitos itens foi preciso adicionar o "RateLimiter" que adiciona um intervalo de 1 segundo entre as solicitações para evitar erros causados por solicitações em excesso
  
  from geopy.extra.rate_limiter import RateLimiter
  geocode = RateLimiter(geolocator.reverse, min_delay_seconds=1)
  df['location'] = df['COORDENADA'].apply(geocode)
  
  # Exporta os endereços requisitados para a planilha endereço
  
  df.to_excel("Endereços.xlsx", sheet_name="endereço")
