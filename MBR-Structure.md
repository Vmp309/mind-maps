
#Tabela 1 – Estrutura da MBR (Master Boot Record)
| Offset (hex) | Tamanho | Campo                        | Descrição                                                  |
|--------------|---------|-----------------------------|------------------------------------------------------------|
| 0x000        | 446 B   | Bootloader                  | Código de inicialização (Bootstrap)                        |
| 0x1BE        | 16 B    | Partição 1                  | Entrada da Tabela de Partição                              |
| 0x1CE        | 16 B    | Partição 2                  | Entrada da Tabela de Partição                              |
| 0x1DE        | 16 B    | Partição 3                  | Entrada da Tabela de Partição                              |
| 0x1EE        | 16 B    | Partição 4                  | Entrada da Tabela de Partição                              |
| 0x1FE        | 2 B     | Assinatura do setor         | Valor fixo 0x55AA (setor de boot válido)                   |

#Tabela 2 – Estrutura de uma Entrada da Tabela de Partições (16 bytes)
| Offset | Tamanho | Campo                  | Descrição                                                    |
|--------|---------|------------------------|--------------------------------------------------------------|
| 0x00   | 1 B     | Status da partição     | 0x80 = ativa (bootável), 0x00 = inativa                      |
| 0x01   | 3 B     | CHS início             | Endereço físico de início (Cylinder-Head-Sector)             |
| 0x04   | 1 B     | Tipo da partição       | Ex: 0x0B = FAT32, 0x07 = NTFS, etc.                          |
| 0x05   | 3 B     | CHS fim                | Endereço físico do fim da partição                           |
| 0x08   | 4 B     | LBA inicial            | Endereço lógico (Logical Block Address) do início da partição|
| 0x0C   | 4 B     | Total de setores       | Tamanho da partição em número de setores                     |

