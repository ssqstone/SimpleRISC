---
# [SimpleRISC](https://github.com/ssqstone/SimpleRISC)

---

## General
** SimpleRISC ** is an optional coursework of one of my favorite class -- High-Performance Computer Systems, lectured by Weiwu Hu, the chief engineer of [Loongson](https://en.wikipedia.org/wiki/Loongson). 

Though very simple with the absence of the executing out-of-order feature and the memory access feature and a very simple ISA, this simple "CPU" implementation employs a full featured in-order pipeline, which is very useful in understanding the essence of the superscalar feature of modern CPU micro-architecture design. 

## The Instruction Set

### Basic Features
 * RISC
 * 16-bit width instructions and data
 * 8 GPR (general purpose registers), #0 GPR is always zero
 * one fixed-point ALU
 
### Instruction Format
 * Register Type
 * Immediate Type

<table class="table table-striped table-bordered">
<tbody>
<tr>
<td>I-Type</td>
<td>OP(4)</td>
<td>RD(3)</td>
<td>RS(3)</td>
<td colspan='2'>Immediate</td>
</tr>
<tr>
<td>R-Type</td>
<td>OP(4)</td>
<td>RD(3)</td>
<td>RS1(3)</td>
<td>RS2(3)</td>
<td>OPX(3)</td>
</tr>
</tbody>
</table>


### Basic Instructions

<table class="table table-striped table-bordered">
<tbody>
<tr>
<td>ADD</td>
<td>0001</td>
<td>rd</td>
<td>rs1</td>
<td>rs2</td>
<td>000 </td>
</tr>
<tr>
<td>SUB</td>
<td>0010</td>
<td>rd</td>
<td>rs1</td>
<td>rs2</td>
<td>000 </td>
</tr>
<tr>
<td>AND</td>
<td>0011</td>
<td>rd</td>
<td>rs1</td>
<td>rs2</td>
<td>000 </td>
</tr>
<tr>
<td>OR</td>
<td>0100</td>
<td>rd</td>
<td>rs1</td>
<td>rs2</td>
<td>000 </td>
</tr>
<tr>
<td>SR</td>
<td>0111</td>
<td>rd</td>
<td>rs1</td>
<td>rs2</td>
<td>000 </td>
</tr>
<tr>
<td>NOT</td>
<td>0101</td>
<td>rd</td>
<td>rs1</td>
<td>rs2</td>
<td>000 </td>
</tr>
<tr>
<td>SRU</td>
<td>1000</td>
<td>rd</td>
<td>rs1</td>
<td>rs2</td>
<td>000 </td>
</tr>
<tr>
<td>SL</td>
<td>0110</td>
<td>rd</td>
<td>rs1</td>
<td>rs2</td>
<td>000 </td>
</tr>
<tr>
<td>BZ</td>
<td>1100</td>
<td>000</td>
<td>rs1</td>
<td colspan='2'>offset</td>
</tr>
<tr>
<td>LD</td>
<td>1010</td>
<td>rd</td>
<td>base</td>
<td colspan='2'>offset</td>
</tr>
<tr>
<td>ST</td>
<td>1011</td>
<td>rd</td>
<td>base</td>
<td colspan='2'>offset</td>
</tr>
<tr>
<td>ADDI</td>
<td>1001</td>
<td>rd</td>
<td>rs1</td>
<td colspan='2'>imm</td>
</tr>
<tr>
<td>BGT</td>
<td>1100</td>
<td>001</td>
<td>rs1</td>
<td colspan='2'>offset</td>
</tr>
<tr>
<td>BLE</td>
<td>1100</td>
<td>010</td>
<td>rs1</td>
<td colspan='2'>offset</td></tr></tbody></table>

### Data Path
After some optimization, the final data path is illustrated below. 

<br/><br/><a target="_blank" href="https://github.com/ssqstone/SimpleRISC/blob/master/datapath.PNG?raw=true"> <img  href="https://github.com/ssqstone/SimpleRISC/blob/master/datapath.PNG?raw=true" style="display: block; margin: auto; width: 50%" src="https://github.com/ssqstone/SimpleRISC/blob/master/datapath.PNG?raw=true"></a><p  style="text-align: center;" > <a target="_blank" href="https://github.com/ssqstone/SimpleRISC/blob/master/datapath.PNG?raw=true"> Data Path </a> </p><br/><br/>

** Note: All the materials are from my class "High-Performance Computer Systems", and all rights reserved. **

<small>This is just a simple course work at the very begining of the course, and the whole course is far more complex than this small course work.</small>
