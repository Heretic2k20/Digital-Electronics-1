# Lab 01 - Gates



![Logo](logolink_eng.jpg)

## Část 1 - GitHub:
**Zde je odkaz na můj git repozítář:** [MyGitHub](https://github.com/Heretic2k20/Digital-Electronics-1)

## Část 2 - De Morganova pravidla: 

**Pravidla:**

*f(c;b;a) = not(b).a + not(c).not(b)*

*f(c;b;a)nand = not{not[not(b).a] . not[not(c).not(b)]}*

*f(c;b;a)nor = not[b + not(a)] + not[c + b]*

####Odkaz na zdrojový kód: [GatesSourcCode](https://www.edaplayground.com/x/wtbF)

####Požadované části zdrojového kódu:**


***Popis "Black-boxu" (Vstupů a výstupů):***

     port(
     
        a_i     : in  std_logic;         -- Data input
        
        b_i     : in  std_logic;         -- Data input
        
        c_i     : in  std_logic;         -- Data input
        
        f_o     : out std_logic;         -- OR output function
        
        fnand_o : out std_logic;         -- AND output function
        
        fnor_o  : out std_logic          -- NOR output function
        
    );


***Architektura (Implementace vzorců):***


    f_o     <= ((not b_i) and a_i) or ((not c_i) and (not b_i));
    
    fnand_o <= not ((not ((not b_i) and a_i)) and (not ((not c_i) and (not b_i))));
    
    fnor_o  <= not (b_i or (not a_i)) or (not (c_i or b_i));
    

###### (xhynst03 - VUT FEKT  |  15.02.2021)
