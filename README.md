# easy_monitor -Version0.2-

This is a simple project for monitoring variables changes, such as loss chages with time in Neural Network training. 

### 0. something about this project

I create this project mainly for the purpose of simpltly monitoring loss and other target variables when training a neural network, without using some heavy libraries (such as Weights & Biases), these libraries are very good, but if you just want to get a simple monitor, you can try this easy_monitor ^_^

This project is based on matplotlib. 

For now, this is just version0.1, only realize single figure for one variable.

### 1. install

There are two ways to install this module, you can directly download code from this repository, or you can install it using pypi as following:

> pip install easy-monitor

### 2. Use Instruction

Using this module to show variable changes is very easy, firstly you should import this module:

> import easy_monitor

Then, before use it, you must instantiated an easy_monitor object, one example is shown below:

![v0.1_example.jpg](https://i.loli.net/2021/11/13/g652rzS3xRGwsdB.jpg)

If you don't need the figure title and plot label, you can directly use the follow code to instantiated it:

![新实例化-自动区间.jpg](https://s2.loli.net/2021/12/04/jHxI1LNCZsBvzqk.jpg)

When you get a new pair data you want to monitor, such as at n epoch, the average loss is n_epoch_loss, then all you need to do to realize the monitor is:

> monitor.ani_plot(n, n_epoch_loss)

And if you don't want the figure being closed when your training is finished, you can add

> monitor.hold_figure()

at the end of your code.

### 3. Detail Parameters for easy_monitor class

In Version 0.1, avaiable parameters for formating figures as following:

![v0.1_easy_monitor-class.jpg](https://i.loli.net/2021/11/13/4epqUlVozLWEsar.jpg)

You can get the meaning of most parameters from their names , below I will explain some ambiguous parameters.

1. frame_pause_time is the time paused between different frames, with unit of second.

2. xlim_lower is the lower bound for x axis in the figure, the default value is None, if you don't assign a value for it, then xlim_lower will be calculated based on the max and min value of x data with a margin_factor as:

   > xlim_lower = xmin - (xmax - xmin) / margin_factor

   xlim_upper, ylim_lower and ylim_upper are the same meaning.

3. margin_factor is used to define the margin we want in the figure.
4. xticks_num or yticks_num is numbers of ticks in x or y axises.
5. lengend_loc is the position of lengend, it can be chosen from upper, lower, left, right and center.
6. x_log or y_log is used to specify if the x or y axis use log scale. 





