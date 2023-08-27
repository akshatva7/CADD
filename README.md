# System Verilog - CADD

## Inverter

```
module inv(input logic [3:0] a,
          output logic [3:0] y);
assign y=~a;
endmodule
```

## 2:1 MUX

If the condition is 1, the operator chooses the first expression. If the condition is 0, the operator chooses the second expression.The following code demonstrates the idiom for a 2:1 multiplexer with 4-bit inputs and outputs using the conditional operator.

```
module mux2(input logic [3:0] d0, d1,
            input logic s,
            output logic [3:0] y);
assign y = s ? d1 : d0;

endmodule
```
## 4:1 MUX

```
module mux4(input logic [3:0] d0, d1,d2,d3
            input logic [1:0] s,
            output logic [3:0] y);
assign y = s[1] ? (s[0] ? d3 : d2): (s[0] ? d1 : d0);
endmodule
```
## Impotant TABLES
### Operators Precendence
<img src = "https://github.com/akshatva7/CADD/assets/135726741/2e2b1695-82ed-49ae-ac05-044328774c29" width="400"/>




## Full Adder
In SystemVerilog, internal signals are usually declared as logic.
```
module fa(input logic a, b, cin,
output logic s, cout);
logic p,g;
assign p = a ^ b;
assign g = a & b;
assign s = p ^ cin;
assign cout = g | (p & cin);
endmodule









