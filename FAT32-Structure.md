# Estrutura do FAT32

## 1. MBR (Master Boot Record)
- Contém:
  - Tabela de Partições
  - Código de Boot

## 2. VBR (Volume Boot Record) / Boot Sector
- Contém:
  - BPB (BIOS Parameter Block)
  - Código de Boot
  - Informações do Sistema de Arquivos

## 3. FSInfo (Setor de Informação)
- Contém:
  - Setor reservado
  - Informação sobre:
    - Espaço livre
    - Próximo cluster livre

## 4. FAT (File Allocation Table)
- Características:
  - Duas cópias redundantes (FAT1 e FAT2)
  - Tabela de alocação de clusters
  - Indicação de:
    - Clusters livres
    - Clusters ocupados
    - Final de arquivo (EOF)

## 5. Área de Dados
- Contém:
  - Arquivos e Diretórios
  - Cada arquivo pode ocupar múltiplos clusters encadeados
  - A raiz do sistema pode estar em qualquer local (diferente do FAT16)

## 6. Diretórios
- Diretório Raiz
- Diretórios Subordinados
- Cada entrada contém:
  - Nome do Arquivo (formato SFN ou LFN)
  - Atributos (diretório, oculto, sistema etc.)
  - Cluster inicial
  - Tamanho do arquivo (em bytes)


#Resumindo:

FAT32

├── 1. MBR (Master Boot Record)

│   └── Tabela de Partições + Código de Boot

│

├── 2. VBR (Volume Boot Record) / Boot Sector

│   ├── BPB (BIOS Parameter Block)

│   ├── Código de Boot

│   └── Informações do Sistema de Arquivos

│

├── 3. FSInfo (Setor de Informação)

│   ├── Setor reservado

│   └── Contém info sobre espaço livre e cluster próximo livre

│

├── 4. FAT (File Allocation Table)

│   ├── 2 cópias redundantes

│   ├── Tabela de alocação de clusters

│   └── Indica quais clusters estão livres, ocupados ou final de arquivo (EOF)

│

├── 5. Área de Dados

│   ├── Diretórios e Arquivos

│   ├── Cada cluster aponta para o próximo

│   └── Raiz do sistema de arquivos pode estar em qualquer lugar (diferente do FAT16)

│

└── 6. Diretórios

|    ├── Diretório Raiz

|    ├── Diretórios Subordinados
    
|    └── Entradas com:
    
|        ├── Nome do Arquivo (8.3 ou LFN)
        
|        ├── Atributos
        
|        ├── Cluster inicial
        
|        └── Tamanho do Arquivo

