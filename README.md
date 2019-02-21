# IA-SPGEMM

IA-SPGEMM is a An Input Auto-tuning Sparse General Matrix-Matrix Multiplication on Multicore and Manycore Architure. 

It is composed of several parts:
- SpGEMM algorithms for COO, DIA and ELL sparse storage format
- Feature extraction and density representation
- MatNet (mix CNN and BP)

All training data comes from SuitSparse Matrix Collection.

The tool extracts all of the features and density representation as inputs of MatNet.

It is easy to use and provide unified interface.

## Getting Started

All the code will soon be open source !!!

In IA-SPGEMM system, the goal is to search an optimal format and algorithm that minimizes computing overhead.

Setting up an IA-SPGEMM is easy.

(1) run SpGEMM code on CPU with auto-tuning in double precision  
```bash
cd ./IA-SPGEMM-CPU_release;
make;
./spgemm-cpu Inputs/matrix_A.mtx Inputs/matrix_B.mtx;
```

(2) run SpGEMM code on GPU with auto-tuning in double precision  
```bash
cd ./IA-SPGEMM-GPU_release;
make;
./spgemm-gpu Inputs/matrix_A.mtx Inputs/matrix_B.mtx;
```

**Intel & AMD CPU example**

<img src="https://github.com/AnonymousPPOPP2019/IA-SPGEMM/blob/master/IA-SPGEMM-CPU_release/1.jpg"/>

**NVIDIA GPU example**

<img src="https://github.com/AnonymousPPOPP2019/IA-SPGEMM/blob/master/IA-SPGEMM-GPU_release/2.jpg"/>

## Requirement
- Intel MKL 2018
- CUSP v0.5.1
- cuSPARSE v8.0
- Python 3.5.2
- tensorflow 1.4.0
- keras 2.1.0

## MatNet
Details of the neural network

Weights are in IA-SPGEMM-CPU_release/NetWeights and IA-SPGEMM-GPU_release/NetWeights

MatNet structure is below:

<img src="https://github.com/AnonymousPPOPP2019/IA-SPGEMM/blob/master/model.png"/>