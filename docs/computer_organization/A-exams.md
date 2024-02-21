# 关于考试

## 2022 期末回忆卷

### 选择题
- 给机器码翻译成指令
- 给32位大立即数地址取出其中内容（lui+lw）
- 浮点数加法过程：$0.12345 \times 10^2$ 和 $0.12345 \times 10^{-2}$ 对齐后 10 的幂次是多少
- 四个选项选对的：
    - PTE 数=物理页数
    - 增加 associativity 可以减少 capa miss
    - async bus 的概念
    - 内存结构中耗时最多的是最上层
- IEEE 754：$1.355-2.105$ 用单精度浮点数表示
- 单周期的时候时钟周期完不成哪个工作(读并写内存)
- TLB 有 tlb 的时候先看谁：tlb pgtbl cache phymem
- RAID 是干啥的
- cache 增大 block size 可以减少哪种 miss
- write through 指什么
- 6 个 block，每个 block 4words，求 840 对应的 block 号


### 大题

#### 1
(1) 把这6个数排序：在原码、补码、符号表示、IEEE754 下的 0xF0000000，在原码、补码下的 0xFFFFFFFF

(2) 不用别的寄存器，交换 x10 和 x11

(3) 书上IndexOutOfBound 那个例子，判断数组越界


#### 2 写汇编

```c
void main(char *s,int *n){
     char c,ch;
     c = '3';
     ch = '5';
     *n = replace(*s,c,ch);
}

int replace(char *u,char c,char ch){
     int i = 0;
     while(u[i]!=0){
          if(u[i]==c){
                u[i]=ch;
                break;
          }
          i++;
     }
     return i;
}
```

#### 3 cache(不确定完全一致)

(1) 32B 的 cache，一个 entry 8B，直接映射，write through+write around，给出如下访问：0 16 48 8 56 16 8 56 32 0 60，问每一次的 index, tag, 是否 hit<br />(注意 write around)

(2) 128B 的 cache，一个 entry 16B，2 路组关联 LRU，write back，给出访问：64 32 64 0 112 64 128 48 240 0，问的跟上面一样，外加最后的 dirty block number


#### 4 虚拟内存
页表大小，以及给定情况问 TLB 能不能容纳 8MiB 内存


#### 5 流水线
(1)先问了 sub 的时候除了 ALUOp 以外各个信号的值

给了一段代码，应该是

```
sub x5,x7,x11  
ld x13, 0(x5)  
ld x7,0(x2)  
add x13,x5,x13  
sd x13, 0(x5)
```

问：

(2) 如果没有 forward 和 hazard detection，在代码插 nop 使其能正确    
(3) 如果有 forward 没有 hazard detection，干(2)的事    
(4) 如果有 forward，写前7个时钟周期 ForwardA 和 ForwardB 的信号值


## 历年卷
- [https://www.cc98.org/topic/5114223](https://www.cc98.org/topic/5114223)
- [https://www.cc98.org/topic/5118209](https://www.cc98.org/topic/5118209)


### 小考点

- Intro & Misc
- Instructions
    - machine code
    - addressing method
    - floating point inst
- Arithmetic
    - 1's complement, 2's complement
    - sign extensions
    - floating point calc steps
    - what is underflow
    - IEEE 754 
- Processor
- Cache
    - write-through, etc.
- Virtual Memory
    - TLB
    - usage of dirty bit
- I/O
    - SCSI Bus, etc.
    - memory-mapped I/O system


### 大题

- 给 C 写汇编 [19(14)]
- Cache 算位数 [19(12)]


<center>![image.png](imgs/1655054029001-a6ad0f7a-ded6-44f9-8ab3-d51797baf14c.png){width=600}</center>
 D
