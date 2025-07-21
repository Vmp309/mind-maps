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
