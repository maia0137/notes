# Bloco de Notas de Campo (GPS + Rumo)

App HTML único, offline, feito para rodar direto no navegador do celular (testado em Samsung A06) — sem instalação, sem servidor. Pensado para anotações em campo de engenharia florestal, com coleta de coordenadas geográficas embutida.

## Funcionalidades

- **Bloco de notas com múltiplas abas**, undo/redo, copiar/colar, compartilhar (Web Share API) e download do arquivo.
- **📍 GPS**: insere um registro espacial com lat/lng decimal, GMS, UTM (SIRGAS2000/WGS84), datum, altitude elipsoidal, acurácia e links prontos para Google Maps, Street View e OSM.
- **🎯 Rastrear Rumo**: modo de rastreamento contínuo (`watchPosition`) que captura rumo de deslocamento e velocidade — **não é bússola/azimute de agrimensura**, é o vetor de movimento (COG) do GPS.
- **Data/Hora**: cada registro de GPS já vem com a data/hora exata do fix (não do momento em que o texto foi inserido).
- **Metadados (Meta)**: insere um cabeçalho YAML (`title`, `data`, `category`, `tags`) no topo da anotação.
- **Modelos prontos**: templates para fichamento bibliográfico, resumo modular e relatórios acadêmicos (ABNT).
- **Ditado por voz** e **Modo Discreto** (tela oculta, útil em campo/sala de aula).
- **Modo Foco** (tela cheia, sem distrações) e **Buscar/Substituir** (inclusive em todas as abas abertas).
- **Zoom de fonte**, alternância de tema (claro/escuro) e instalação como app offline (PWA).

## Como usar

1. Abra o `.html` no navegador do celular (ou acesse via GitHub Pages).
2. Toque em **GPS** para um ponto único, ou em **Rastrear Rumo** para capturar rumo + velocidade (ande alguns passos em linha reta antes de tocar de novo).
3. Use **Meta** e **Modelos** para estruturar relatórios acadêmicos a partir das anotações de campo.

## Limitações conhecidas

- Acurácia depende do GPS do aparelho (tipicamente ±3m a ±20m em céu aberto).
- Altitude é **elipsoidal (WGS84)**, não altitude acima do nível do mar — para altitude ortométrica, aplique um modelo de ondulação geoidal (ex. MAPGEO2015/IBGE) sobre o valor.
- O rótulo "SIRGAS2000/WGS84" é uma aproximação de engenharia (diferença centimétrica); a API do navegador só garante WGS84.
- "Rumo" só é confiável com o aparelho em movimento (idealmente ≥1 m/s); parado, o valor pode ser ruído.
