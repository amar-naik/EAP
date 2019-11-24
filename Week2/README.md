
Week 2 assignment details

Code : Week2/Code9.ipynb

Logs of 20 epochs

Epoch 1/20

Epoch 00001: LearningRateScheduler setting learning rate to 0.003.
60000/60000 [==============================] - 127s 2ms/step - loss: 0.5153 - acc: 0.8567 - val_loss: 0.0854 - val_acc: 0.9819
Epoch 2/20

Epoch 00002: LearningRateScheduler setting learning rate to 0.0022744503.
60000/60000 [==============================] - 126s 2ms/step - loss: 0.2487 - acc: 0.9267 - val_loss: 0.0556 - val_acc: 0.9877
Epoch 3/20

Epoch 00003: LearningRateScheduler setting learning rate to 0.0018315018.
60000/60000 [==============================] - 126s 2ms/step - loss: 0.1980 - acc: 0.9403 - val_loss: 0.0410 - val_acc: 0.9899
Epoch 4/20

Epoch 00004: LearningRateScheduler setting learning rate to 0.0015329586.
60000/60000 [==============================] - 124s 2ms/step - loss: 0.1668 - acc: 0.9474 - val_loss: 0.0506 - val_acc: 0.9862
Epoch 5/20

Epoch 00005: LearningRateScheduler setting learning rate to 0.0013181019.
60000/60000 [==============================] - 125s 2ms/step - loss: 0.1534 - acc: 0.9495 - val_loss: 0.0341 - val_acc: 0.9912
Epoch 6/20

Epoch 00006: LearningRateScheduler setting learning rate to 0.0011560694.
60000/60000 [==============================] - 125s 2ms/step - loss: 0.1413 - acc: 0.9509 - val_loss: 0.0304 - val_acc: 0.9909
Epoch 7/20

Epoch 00007: LearningRateScheduler setting learning rate to 0.0010295127.
60000/60000 [==============================] - 125s 2ms/step - loss: 0.1320 - acc: 0.9515 - val_loss: 0.0242 - val_acc: 0.9946
Epoch 8/20

Epoch 00008: LearningRateScheduler setting learning rate to 0.0009279307.
60000/60000 [==============================] - 125s 2ms/step - loss: 0.1225 - acc: 0.9533 - val_loss: 0.0246 - val_acc: 0.9932
Epoch 9/20

Epoch 00009: LearningRateScheduler setting learning rate to 0.0008445946.
60000/60000 [==============================] - 124s 2ms/step - loss: 0.1187 - acc: 0.9552 - val_loss: 0.0226 - val_acc: 0.9943
Epoch 10/20

Epoch 00010: LearningRateScheduler setting learning rate to 0.0007749935.
60000/60000 [==============================] - 124s 2ms/step - loss: 0.1142 - acc: 0.9553 - val_loss: 0.0278 - val_acc: 0.9915
Epoch 11/20

Epoch 00011: LearningRateScheduler setting learning rate to 0.0007159905.
60000/60000 [==============================] - 125s 2ms/step - loss: 0.1120 - acc: 0.9547 - val_loss: 0.0207 - val_acc: 0.9942
Epoch 12/20

Epoch 00012: LearningRateScheduler setting learning rate to 0.000665336.
60000/60000 [==============================] - 126s 2ms/step - loss: 0.1049 - acc: 0.9569 - val_loss: 0.0227 - val_acc: 0.9927
Epoch 13/20

Epoch 00013: LearningRateScheduler setting learning rate to 0.0006213753.
60000/60000 [==============================] - 125s 2ms/step - loss: 0.1031 - acc: 0.9573 - val_loss: 0.0202 - val_acc: 0.9938
Epoch 14/20

Epoch 00014: LearningRateScheduler setting learning rate to 0.0005828638.
60000/60000 [==============================] - 125s 2ms/step - loss: 0.1036 - acc: 0.9559 - val_loss: 0.0199 - val_acc: 0.9949
Epoch 15/20

Epoch 00015: LearningRateScheduler setting learning rate to 0.0005488474.
60000/60000 [==============================] - 125s 2ms/step - loss: 0.1031 - acc: 0.9561 - val_loss: 0.0208 - val_acc: 0.9937
Epoch 16/20

Epoch 00016: LearningRateScheduler setting learning rate to 0.0005185825.
60000/60000 [==============================] - 125s 2ms/step - loss: 0.0989 - acc: 0.9561 - val_loss: 0.0216 - val_acc: 0.9935
Epoch 17/20

Epoch 00017: LearningRateScheduler setting learning rate to 0.000491481.
60000/60000 [==============================] - 125s 2ms/step - loss: 0.0980 - acc: 0.9565 - val_loss: 0.0239 - val_acc: 0.9926
Epoch 18/20

Epoch 00018: LearningRateScheduler setting learning rate to 0.0004670715.
60000/60000 [==============================] - 124s 2ms/step - loss: 0.0953 - acc: 0.9567 - val_loss: 0.0182 - val_acc: 0.9950
Epoch 19/20

Epoch 00019: LearningRateScheduler setting learning rate to 0.0004449718.
60000/60000 [==============================] - 124s 2ms/step - loss: 0.0944 - acc: 0.9584 - val_loss: 0.0218 - val_acc: 0.9934
Epoch 20/20

Epoch 00020: LearningRateScheduler setting learning rate to 0.000424869.
60000/60000 [==============================] - 125s 2ms/step - loss: 0.0939 - acc: 0.9586 - val_loss: 0.0182 - val_acc: 0.9949

Result of model.evaluate

[0.01818705277298577, 0.9949]

Strategy

Plan was to understand the difference between the 8 codes given in this assignment.Noting high level observations below

https://docs.google.com/spreadsheets/d/1h55ivLJQcw70GOzuPLpsNS-stCxTdUEWllb8faZJKnY/edit?usp=sharing


Common
All the programs have input shape of (28,28,1) in the first layer of sequential model
Convolution filter size of 3 X 3 applied in the first step
RELU activation function is used

Difference
Convolution filters used in the programs vary (ie. 32, 16, 10 filters used)
Also at each step of convolution the filter size is changed in each program
Except first program, in all other programs max pooling is applied

To achieve the output of 99.4% accuracy with less than 15k params
Changed the convolution filters in the sequential model to see if total params is less than 15k params
Post that the focus was on model evaluation so that accuracy of 99.4 was also done.
Also was observing accuracy at each epoch to ensure that it is not stagnant
Post achieving the accuracy, understood that by default bias is set to true if it is no specified. Hence enabled use_bias= False And run the program again since accuracy changed
