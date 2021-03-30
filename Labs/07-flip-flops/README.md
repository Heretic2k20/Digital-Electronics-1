# Lab 07 - Flips Flops

![Logo](images/logolink_eng.jpg)

## Část 1 - Domácí příprava:
------------------------------------------------------------------------

**Tabulky:**

   | **clk** | **d** | **q(n)** | **q(n+1)** | **Comments** |
   | :-: | :-: | :-: | :-: | :-- |
   | 0 | 0 | 0 | 0 | Vzorkovány a uloženy   |
   | 0 | 0 | 1 | 0 | Vzorkovány a uloženy   |
   | 1 | 1 | 0 | 1 | Vzorkovány a uloženy   |
   | 1 | 1 | 1 | 1 | Vzorkovány a uloženy   |
   
   
   | **clk** | **j** | **k** | **q(n)** | **q(n+1)** | **Comments** |
   | :-: | :-: | :-: | :-: | :-: | :-- |
   | 0 | 0 | 0 | 0 | 0 | Beze změny  |  
   | 0 | 0 | 0 | 1 | 1 | Beze změny  |
   | 0 | 0 | 0 | 1 | 0 | Reset       |
   | 0 | 0 | 1 | 1 | 0 | Reset       |
   | 1 | 1 | 0 | 0 | 1 | Set         |
   | 1 | 1 | 0 | 1 | 1 | Set         |
   | 1 | 1 | 1 | 0 | 1 | Toggle      |
   | 1 | 1 | 1 | 1 | 0 | Toggle      |
   
   
   | **clk** | **t** | **q(n)** | **q(n+1)** | **Comments** |
   | :-: | :-: | :-: | :-: | :-- |
   | 0 | 0 | 0 | 0 | Beze změny        |
   | 0 | 0 | 1 | 1 | Beze změny 	     |
   | 1 | 1 | 0 | 1 | Invertovaný       |
   | 1 | 1 | 1 | 0 | Invertovaný       |
   
   
   ###### (xhynst03 - VUT FEKT  |  30.03.2021)
  
