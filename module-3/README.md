[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/vYQ4W4rf)
# MiniTorch Module 3

<img src="https://minitorch.github.io/minitorch.svg" width="50%">

* Docs: https://minitorch.github.io/

* Overview: https://minitorch.github.io/module3.html


You will need to modify `tensor_functions.py` slightly in this assignment.

* Tests:

```
python run_tests.py
```

* Note:

Several of the tests for this assignment will only run if you are on a GPU machine and will not
run on github's test infrastructure. Please follow the instructions to setup up a colab machine
to run these tests.

This assignment requires the following files from the previous assignments. You can get these by running

```bash
python sync_previous_module.py previous-module-dir current-module-dir
```

The files that will be synced are:

        minitorch/tensor_data.py minitorch/tensor_functions.py minitorch/tensor_ops.py minitorch/operators.py minitorch/module.py minitorch/autodiff.py minitorch/module.py project/run_manual.py project/run_scalar.py project/run_tensor.py

## Module 3.1/3.2 - Parallel_check logs

The output can be found in the file parallel_check_output.txt

## Module 3.4 - Fast vs CUDA

<img src="3.4_fast_vs_cuda.png">

## Module 3.5 Training:
 ### Simple:
 ```
 !cd $DIR; PYTHONPATH=/content/$DIR python3.8 project/run_fast_tensor.py --BACKEND cpu --HIDDEN 100 --DATASET simple --RATE 0.05
 ```

Epoch  490  loss  0.0365964801049523 correct 50
A single epoch completed on average in 0.23 seconds \


 ```
 !cd $DIR; PYTHONPATH=/content/$DIR python3.8 project/run_fast_tensor.py --BACKEND gpu --HIDDEN 100 --DATASET simple --RATE 0.05
 ```

Epoch  490  loss  1.278239609772305e-05 correct 50
A single epoch completed on average in 2.37 seconds \

 ### Split:
 ```
 !cd $DIR; PYTHONPATH=/content/$DIR python3.8 project/run_fast_tensor.py --BACKEND cpu --HIDDEN 100 --DATASET split --RATE 0.05
 ```

Epoch  490  loss  2.0643161209333045 correct 50
A single epoch completed on average in 0.10 seconds \

 ```
!cd $DIR; PYTHONPATH=/content/$DIR python3.8 project/run_fast_tensor.py --BACKEND gpu --HIDDEN 200 --DATASET split --RATE 0.1
 ```


Epoch  490  loss  1.9395216131891275 correct 49
A single epoch completed on average in 2.53 seconds \

 ### XOR:

 ```
 !cd $DIR; PYTHONPATH=/content/$DIR python3.8 project/run_fast_tensor.py --BACKEND cpu --HIDDEN 100 --DATASET xor --RATE 0.05
 ```

 
Epoch  490  loss  1.623783119985716 correct 50
A single epoch completed on average in 0.11 seconds \

 ```
!cd $DIR; PYTHONPATH=/content/$DIR python3.8 project/run_fast_tensor.py --BACKEND gpu --HIDDEN 200 --DATASET xor --RATE 0.1
 ```


Epoch  490  loss  0.14887388571151505 correct 50
A single epoch completed on average in 2.49 seconds \

 ### Big model:

 ```
 !cd $DIR; PYTHONPATH=/content/$DIR python3.8 project/run_fast_tensor.py --BACKEND cpu --HIDDEN 200 --DATASET simple --RATE 0.05
 ```

Epoch  490  loss  0.13295306473930626 correct 50
A single epoch completed on average in 0.42 seconds \

 ```
 !cd $DIR; PYTHONPATH=/content/$DIR python3.8 project/run_fast_tensor.py --BACKEND gpu --HIDDEN 200 --DATASET simple --RATE 0.05
 ```


Epoch  490  loss  0.14898088234425003 correct 50
A single epoch completed on average in 2.53 seconds \
