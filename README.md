# Keras Subpixel Convolution 2D

Returns a Keras layer to do subpixel convolution.

NOTE: Tensorflow backend only. Uses tf.depth_to_space

### Ref
- Real-Time Single Image and Video Super-Resolution Using an Efficient Sub-Pixel Convolutional Neural Network. (Shi et Al.) [https://arxiv.org/abs/1609.05158]


### Requirements
(Please see `requirements.txt` for latest update)

````
    Keras==2.0.2
    tensorflow==1.1.0
````

### Useage
````

    # Subpixel Conv will upsample from (h, w, c) to (h/r, w/r, c/r^2)

    scale = 4
    inputs = Input(shape=input_shape)
    
    x = Convolution2D(channels * scale ** 2, (3, 3), 
        activation='relu', 
        name='conv3x3')(inputs)

    out = SubpixelConv2D(input_shape, scale=scale)(x)

    model = Model(inputs=inputs, outputs=out)
````

### LICENSE
MIT
