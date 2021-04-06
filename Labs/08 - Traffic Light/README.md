# Lab 08 - Traffic Lights

![Logo](images/logolink_eng.jpg)

## Část 1 - Příprava:

**Předpřipravené tabulky**

| **Input P** | `0` | `0` | `1` | `1` | `0` | `1` | `0` | `1` | `1` | `1` | `1` | `0` | `0` | `1` | `1` | `1` |
| :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-:| :-: | :-: | :-: | :-: | :-: |
| **State** | A | A | B | C | C | D | A | B | C | D | B | B | B | C | D | B |
| **Output R** | `0` | `0` | `0` | `0` | `0` | `1` | `0` | `0` | `0` | `1` | `0` | `0` | `0` | `0` | `1` | `0` |

| **RGB LED** | **Artix-7 pin names** | **Red** | **Yellow** | **Green** |
| :-: | :-: | :-: | :-: | :-: |
| LD16 | N15, M16, R12 | `1,0,0` | `1,1,0` | `0,1,0` |
| LD17 | N16, R11, G14 | `1,0,0` | `1,1,0` | `0,1,0` |

**Zapojení**

![Scheme](images/zapojeni02.png)


## Část 2 - Semafory:

**Stavový diagram**

![State-Diagram](images/Scheme.jpg)

### Process p_traffic_fsm

```vhdl
p_traffic_fsm : process(clk)
    begin
        if rising_edge(clk) then
            if (reset = '1') then
                s_state <= STOP1; 
                s_cnt   <= c_ZERO;     

            elsif (s_en = '1') then
                
                case s_state is

                    when STOP1 =>
                        if (s_cnt < c_DELAY_1SEC) then
                            s_cnt <= s_cnt + 1;
                        else
                            s_state <= WEST_GO;
                            
                            s_cnt   <= c_ZERO;
                        end if;

                    when WEST_GO =>
                        if (s_cnt < c_DELAY_4SEC) then
                            s_cnt <= s_cnt + 1;
                        else
                            s_state <= WEST_WAIT;
                            
                            s_cnt   <= c_ZERO;
                        end if;
                   
                    when WEST_WAIT =>
                        if (s_cnt < c_DELAY_2SEC) then
                            s_cnt <= s_cnt + 1;
                        else
                            s_state <= STOP2;
                            
                            s_cnt   <= c_ZERO;
                        end if;
                    
                    when STOP2 =>
                        if (s_cnt < c_DELAY_1SEC) then
                            s_cnt <= s_cnt + 1;
                        else
                            s_state <= SOUTH_GO;
                            
                            s_cnt   <= c_ZERO;
                        end if;

                    when SOUTH_GO =>
                        if (s_cnt < c_DELAY_4SEC) then
                            s_cnt <= s_cnt + 1;
                        else
                            s_state <= SOUTH_WAIT;
                            
                            s_cnt   <= c_ZERO;
                        end if;
                   
                    when SOUTH_WAIT =>
                        if (s_cnt < c_DELAY_2SEC) then
                            s_cnt <= s_cnt + 1;
                        else
                            s_state <= STOP1;
                            
                            s_cnt   <= c_ZERO;
                        end if;
                    
                    when others =>
                        s_state <= STOP1;

                end case;
            end if;
        end if;
    end process p_traffic_fsm;
```

### process p_output_fsm

```vhdl
p_output_fsm : process(s_state)
    begin
        case s_state is
            when STOP1 =>
                south_o <= "100";   -- Red
                west_o  <= "100";   -- Red
            
            when WEST_GO =>
                south_o <= "100";   -- Red
                west_o  <= "010";   -- Green
           
            when WEST_WAIT =>
                south_o <= "100";   -- Red
                west_o  <= "110";   -- Yellow
            
            when STOP2 =>
                south_o <= "100";   -- Red
                west_o  <= "100";   -- Red 
            
            when SOUTH_GO =>
                south_o <= "010";   -- Green 
                west_o  <= "100";   -- Red 
            
            when SOUTH_WAIT =>
                south_o <= "110";   -- Yellow 
                west_o  <= "100";   -- Red 

            when others =>
                south_o <= "100";   -- Red
                west_o  <= "100";   -- Red
        end case;
    end process p_output_fsm;
```

### Screenshot simulace

![Simulace01](images/simulation01.png)

![Simulace02](images/simulation02.png)


## Část 2 - Chytré řízení:

### Tabulky


### Schéma






###### (xhynst03 - VUT FEKT  |  15.02.2021)
