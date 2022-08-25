---
title: Control_Typical_Block
subtitle: This post describes the basic contents of automatic control theory.

# Summary for listings and search engines
summary: This post describes the basic contents of automatic control theory.

tags: 
- Control System
- Automatic Control Theory

categories: 
- Automatic Control Theory

# Date published
date: '2022-03-21'

# Date updated
lastmod: '2022-03-21'
math: true
---

## 1 Typical Components
The so-called component is the classification of original components with the same form transfer function. These transfer functions are the most classical and typical of control systems.

### 1.1 Proportional Component
Transfer function
$$
G(s) = K
$$

This system is to multiply the input by a constant K and then output, so it is called the proportional component. A typical proportional component is a potentiometer, which has a corresponding proportional output according to the position of the resistance pointer.

### 1.2 Differential Component
Transfer function
$$
G(s) = s
$$

It is not difficult to find that this is the Laplace transform differential theorem. Multiplying the input by s is the differential in the time domain.

### 1.3 Integral Component
Transfer function
$$
G(s) = \frac{1}{s}
$$

This is also the integral theorem of Laplace transform. Dividing the input by s is the integral in the time domain.

### 1.4 Inertia Component
Transfer function
$$
G(s) = \frac{1}{Ts+1}
$$

This function actually describes a process of slow disappearance. We write its time-domain function.
$$
h(t) = \frac{1}{T}e^{-\frac{t}{T}}
$$

With the increase of time, the function value decreases exponentially, just like it keeps a distance due to inertia, and finally disappears. Where $T$ is the **time constant**, which determines the decay speed of the system.

### 1.5 Sscillation Component
Transfer function
$$
G(s) = \frac{1}{T^2s^2+2\xi Ts+1}
$$

The function describes a state of oscillation, which will be described in detail in the second-order system response analysis later.

### 1.6 First-order Composite Differential Component
Transfer function
$$
\tau s+1
$$


### 1.7 Second-order Composite Differential Component
Transfer function
$$
\tau^2s^2+2\xi \tau s+1
$$


### 1.8 Summary
Any transfer function can be regarded as a combination of typical components, which can form a variety of systems.

## 2 Load Effect Problem
Now consider that two circuits are connected together, and the first stage circuit inputs $u_r$, output $u_a$, second stage circuit input $u_a$, output $u_c$。 However, we all know that if two circuits are simply coupled, the second stage circuit will actually affect the first stage circuit, which is called load effect. When the load is connected to the system, the system may not have a simple input-output relationship.

## 3 System Block Diagram
One way to describe the control system is to use the block diagram, in which the flow direction of the signal is represented by the directed line segment, the system module is represented by the box, and the adder is represented by the circle. The block diagram indicates the flow of signals and the processing of signals by various parts.

With the block diagram of the system, the next step is to solve the transfer function of the whole system.

## 4 Transfer Function Solution
### 4.1 Digestion Coefficient Method
Write all the signals in the block diagram, write the relationship between the input and output of the module according to the signal processing, and then eliminate all the intermediate variables to obtain the relationship between the final output and the input. This method is the simplest, but it is not easy when the system becomes very complex.

### 4.2 Equivalent Transformation Method
There are many equivalent transformation rules in the structure diagram. Flexible use of them can find out the transfer function of the system. This process is also called simplification.

#### 4.2.1 Feedback equivalence
The forward module of the system is $G(s)$, the feedback module is $H(s)$, and the system is equivalent to

$$
\frac{G(s)}{1+G(s)H(s)}
$$

<div align=center> 
<img src="https://pic.imgdb.cn/item/62209e4f5baa1a80abc346de.jpg"></img>
<div align=left>


#### 4.2.2 Series equivalence
System $G_1(s)$ and $G_2(s)$ in series, equivalent to

$$
G_1(s)\cdot G_2(s)
$$

<div align=center> 
<img src="https://pic.imgdb.cn/item/62209dfd5baa1a80abc3158d.jpg"></img>
<div align=left>

#### 4.2.3 Parallel equivalence
System $G_1(s)$ and $G_1(s)$ parallel connection, equivalent to

$$
G_1(s)+G_2(s)
$$

#### 4.3.4 Comparison point forward
> The adder is also called a comparator because it subtracts two input signals (signal 1 plus negative signal 2)

The comparison point is after $G(s)$, which is equivalent to that the signal will pass through $G(s)$ after the forward shift without passing $G(s)$. At this time, it needs to be multiplied by the inverse system $\frac{1}{G(s)}$.

<div align=center> 
<img src="https://pic.imgdb.cn/item/62209e425baa1a80abc33dc6.jpg"></img>
<div align=left>

#### 4.3.5 Comparison point backward
On the other hand, the comparison point was originally in front of $G(s)$, which is equivalent to passing $G(s)$. After moving back, it did not pass $G(s)$, so you need to add a $G(s)$.

<div align=center> 
<img src="https://pic.imgdb.cn/item/62209e125baa1a80abc32422.jpg"></img>
<div align=left>

#### 4.3.6 Lead out point forward
If the lead out point is behind the system, the original signal has passed through the system. If it is moved to the front, it is equivalent to being led out without passing through the system, and a $G(s)$ needs to be added.

<div align=center> 
<img src="https://pic.imgdb.cn/item/62209e245baa1a80abc32da1.jpg"></img>
<div align=left>

#### 4.3.7 Lead out point backward
If the leading point is in front of the system, the original signal does not pass through the system. After moving to the back, it is equivalent to passing through the system before being led out. Therefore, it needs to be multiplied by an inverse system $\frac{1}{G(s)}$.

<div align=center> 
<img src="https://pic.imgdb.cn/item/62209e375baa1a80abc338b6.jpg"></img>
<div align=left>