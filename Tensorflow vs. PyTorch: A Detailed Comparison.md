## Introduction <a name="introduction"></a>

Deep learning is a common technique of solving real-world problems using human-like computers. 

Deep learning tasks involve the creation of special brain-like architectures known as *artificial neural networks*. 

To help develop such architectures, various Python frameworks for performing deep learning tasks have been developed, making it easier to build and train diversified artificial neural networks. 

The two most popular frameworks for performing deep learning tasks are TensorFlow and PyTorch. 

If you've ever done a deep learning task, you must have heard about the above  terms. 

Maybe, you've been trying to figure out which one to choose, or you're just starting your deep learning journey and you're asking yourself this question...

"Which one is better?"

This forms the subject of discussion in this tutorial. 

I'll be resolving all your doubts about these two popular frameworks and help you choose the one that suits your needs. 

## Table of Contents

You can skip to a specific section of this tutorial using the table of contents below:

[Introduction](#introduction)

[What is Tensorflow?](#what-tensor)

[TensorFlow Code Style](#tensor-style)

[What is PyTorch?](#what-pytorch?)

[PyTorch Code Style ](#pytorch-style)

[TensorFlow vs. PyTorch](#tensorflow-pytorch)

  - [Style](#style)
  
  - [Computation Graphs](graphs)
  
  - [Debugging](#debugging)
  
  - [Community Support](#support)
  
  - [Visualization Tools](#visualization)
  
  - [Deployment](#deployment)
  
  - [Data Parallelism](#parallelism)
  
  - [Prototyping and Production](#prototyping)
  
 [Conclusion](#conclusion) 
  

## What is TensorFlow? <a name="what-tensor"></a>

TensorFlow is an open source framework developed and released by Google in 2015. 

The name "TensorFlow" describes a way of organizing and performing operations on data. 

Both TensorFlow and PyTorch use *tensor* as the basic data structure. 

When using TensorFlow, you perform operations on data stored in tensors by creating a stateful dataflow graph, which is a type of a flowchart that remembers the past events. 

TensorFlow is a production-grade deep learning library. 

It has an established base of active users and many third-party tools and platforms for deploying, training, and serving models. 

## TensorFlow Code Style <a name="tensor-style"></a>

To demonstrate how TensorFlow works, lets create two tensors and multiply them. 

First, let's install TensorFlow using the pip package manager:

Update pip:

```
pip install --upgrade pip
```

Now, run the following command to install TensorFlow:

```
pip3 install --upgrade tensorflow
```

Next, let's import TensorFlow into our workspace:

```
import tensorflow as tf
```

We can now create two tensors, `a` and `b` using the Python list notation:

```
a = [[3., 4., 8.]]
b = [[2.], [3.], [9.]]
```

Let's now invoke the `.multiply()` function to multiply the values of the two tensors and assign the result to the variable `output`:

```
output = tf.multiply(a, b)
```
Let's create a session and invoke the `.run()` function to compile the model:

```
s=tf.Session()

print(s.run(output))
```

The code will return the following array:

![](Capture1.png)

We have used the `tf.multiply()` function to perform element-wise multiplication. 

That's how you can use TensorFlow to multiply tensors. 

## What is PyTorch? <a name="what-pytorch"></a>

PyTorch is a product of Facebook and it was released in 2016. 

PyTorch was developed with the goal of providing production optimizations similar to TensorFlow and make models easier to write. 

It is mostly used in research than in production. 

PyTorch is based on Torch, a C framework for doing fast computation. 

Torch comes with a wrapper written in Lua scripting language for construction of models. 

PyTorch wraps a similar C back end in a Python interface. 

However, PyTorch is more than a wrapper. 

It was written from the ground up with the goal of making it easy for Python programmers to write models. 

Its underlying C/C++ code has been optimized to run Python code. 

Due to the tight integration, you get the following features:

- Better memory management and optimization. 

- Simple error messages. 

- A finer-grained control of the model structure. 

- A more transparent model behavior. 

- Finer compatibility with NumPy. 

## PyTorch Code Style <a name="pytorch-style"></a>


With PyTorch, you can write highly customizable neural network components directly in Python without using many low-level functions. 

It's easy for you to switch between `torch.Tensor` objects and `numpy.array` objects. 

To demonstrate this, let's create two NumPy arrays and convert them into tensors. 

First, install torch and NumPy using pip:

```
pip3 install torch

pip3 install numpy
```

Next, let's import the two libraries:

```
import torch

import numpy as np
```

We can now invoke the NumPy's `.array()` function to create two NumPy arrays, `a` and `b`:

```
a = np.array([[3., 6., 8.]])

b = np.array([[1.], [3.], [6.]])
```

We will use the `torch.from_numpy()` function to turn each `numpy.array` object into a `torch.Tensor` object. 

We will then multiply them using the `torch.mul()` function and store the result in the variable `output`:

```
output = torch.mul(torch.from_numpy(a), torch.from_numpy(b))
```

Let's print out the resulting `torch.Tensor` object as a `numpy.array` object using the `.numpy()` function:

```
print(output.numpy())
```

The code should return the following output:

![](Capture2.png)

You've successfully created two arrays and converted them into tensors. 

## TensorFlow vs. PyTorch <a name="tensorflow-pytorch"></a>

Now that you've grasped the basics of how the two frameworks work, it is time to know the differences between the two. 

This will help you arrive at a decision on which framework to choose for your deep learning projects. 

### Style <a name="style"></a>

If you're an experienced Python programmer, PyTorch will feel easy for you. 

PyTorch is more native to Python, making it easy for developers to develop deep learning models. 

On the other hand, TensorFlow has many entities like placeholders, sessions and more, which may make it a bit complex to learn.

However, unlike PyTorch, TensorFlow supports other coding languages like Swift and JavaScript. 

### Computation Graphs <a name="graphs"></a>

In deep learning and artificial neural networks, computation graphs provide a way to represent the evaluation of mathematical expressions using the graph data structure. 

The two libraries differ in terms of how the computational graphs are defined and used. 

TensorFlow uses a static graph for computation, which means the entire computation graph should be defined before execution is done. 

However, PyTorch is different. It allows you to define and manipulate computational graphs dynamically, making it the best option when dealing with inputs that change in real-time when working with artificial neural networks. 

### Debugging <a name="debugging"></a>

As we stated above, computational graphs are very dynamic when working with PyTorch. 

Due to this, any Python debugging tool like pdb or ipdb can be used to debug code effectively. 

For TensorFlow, you've to install a separate tool called "tfdbg" to be able to evaluate TensorFlow expressions at runtime. 

Note that you cannot debug the code natively with Python, hence, you must install this tool. 

### Community Support <a name="support"></a>

Most people are curious to learn deep learning, and that's why the deep learning community is highly revered. 

A larger community means the ability to find solutions and help easily and quickly. 

TensorFlow has a larger community compared to PyTorch. 

The reason is that PyTorch is newer to the market than TensorFlow, hence, there has been more content online about TensorFlow than PyTorch. 

However, since people have realized how easy it is to use PyTorch, its user community may grow and surpass that of TensorFlow. 

Next, we'll be exploring how these two frameworks differ in terms of visualization tools. 

### Visualization Tools <a name="visualization"></a>

TensorFlow comes with a great visualization tool named "TensorBoard". 

TensorBoard allows you to visualize your machine learning models on the web browser. 

TensorBoard provides numerous visualizations and appealing graphs that can be understood easily. 

PyTorch doesn't have such a tool, hence, to visualize your data, you must use a tool like Matplotlib. 

Although you can still use TensorBoard in PyTorch, the process of integrating the two tools is complex. 

### Deployment<a name="deployment"></a>

TensorFlow wins when it comes to deployment because it comes with a framework named "TensorFlow Serving" that helps us to rapidly deploy models to gRPC servers with much ease. 

In PyTorch, you can achieve a similar result when you use it with Flask or other REST APIs that have been built on top of the model. 

You can also use TensorFlow with the REST APIs, hence, TensorFlow wins when it comes to deployment. 

### Data Parallelism <a name="parallelism"></a>

In this case, parallelism has to do with supporting a pipeline for the distribution of data instead of leaving one entity to process the data. 

PyTorch provides its users with better parallelism capabilities. 

PyTorch users use `Torch.nn.Parallel` to wrap modules that are to be used parallely over other batch data. 

This makes it easy to harness the power of multiple GPUs simulateneously without much effort. 

TensorFlow also offers parallelism. However, it requires several manual implementations that make it complex to use in both learning and production environments. 

### Prototyping and Production <a name="prototyping"></a>

TensorFlow has an advantage as far as building scalable production models is concerned. 

However, the feature should be easy to learn and implement, and PyTorch excels in this. 

It makes it easy to create prototypes and work on projects that have a less production implementation. 


With the above information, you can know which framework, whether TensorFlow or PyTorch, suits your needs. 

## Conclusion: <a name="conclusion"></a>

This is what you've learnt in this article:

- TensorFlow and PyTorch are the two most popular frameworks for performing deep learning tasks. 

- Deep learning involves solving real-world problems using human-like computers. 

- TensorFlow was developed by Google, while PyTorch was developed by Facebook. 

- PyTorch is a new deep learning framework, hence, not much information about it is available online compared to TensorFlow.

- PyTorch is easier to use that TensorFlow, and it is more native to Python. 



































































