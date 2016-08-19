main.py
======
### Process
#### flags
```python
flags = tf.app.flags
flags.DEFINE_string('name', init, 'explanation')
flags.DEFINE_boolean('name', init, 'explanation')
flags.DEFINE_integer('name', init, 'explanation')
...
FLAGS = flags.FLAGS
```
#### set random seed
```python
tf.set_random_seed(FLAGS.random_seed)
random.seed(FLAGS.random_seed)
```

#### main function
```python
with tf.Session(config=tf.ConfigPorto(...))
  config = ..., env = ...
  agent(config, env, sess)
  if FLAGS.is_train:
    agent.train()
  else:
    agent.play()
````

### Note
#### tf.app.run()
  * [source code](https://github.com/tensorflow/tensorflow/blob/master/tensorflow/python/platform/app.py)  
  * explanation: deal with the flags and run the main function

#### Flags.gpu_fraction
  * [How to prevent tensorflow from allocating the totality of a GPU memory?](http://ppt.cc/R6Ruc)
