Code file is : https://github.com/amar-naik/EAP/blob/master/Week3/ASSG3.ipynb


1.

For Given Program , the Accuracy on test data is: 82.62 . Total params: 1,172,410


New modified Program, the Accuracy on test data is: 82.24 . Total params: 98,326

In New modified Program, Epoch 48/50 is below

195/195 [==============================] - 24s 124ms/step - loss: 0.2738 - acc: 0.9017 - val_loss: 0.5806 - val_acc: 0.8329



2.  model definition (model.add... ) with output channel size and receptive field is below :


model = Sequential()
model.add(SeparableConv2D(30, kernel_size=(3,3), input_shape=(32, 32, 3), activation = 'relu')) #32X32X30 ,RF=3X3
model.add(BatchNormalization())

model.add(SeparableConv2D(48, kernel_size=(3,3), activation = 'relu')) #30X30X48 ,RF=5X5
model.add(BatchNormalization())

model.add(MaxPooling2D(pool_size=(2, 2))) #15X15X48 ,RF=6X6
model.add(Dropout(0.25))

model.add(SeparableConv2D(96, kernel_size=(3,3), border_mode='same', activation = 'relu')) #15X15X96 ,RF=10X10
model.add(BatchNormalization())


model.add(SeparableConv2D(96, kernel_size=(3,3), border_mode='same', activation = 'relu')) #13X13X96 ,RF=14X14
model.add(BatchNormalization())

model.add(SeparableConv2D(96, kernel_size=(3,3), activation = 'relu')) #11X11X96 ,RF=18X18
model.add(BatchNormalization())


model.add(MaxPooling2D(pool_size=(2, 2))) #5X5X96 ,RF=20x20
model.add(Dropout(0.25))

model.add(SeparableConv2D(192, kernel_size=(3,3), activation = 'relu', border_mode='same')) #5X5X192 ,RF=28x28
model.add(BatchNormalization())

model.add(SeparableConv2D(225, kernel_size=(3,3), activation = 'relu')) #3X3X225 ,RF=36x36
model.add(BatchNormalization())

model.add(MaxPooling2D(pool_size=(2, 2))) #1X1X225 ,RF=40x40
model.add(Dropout(0.25))

model.add(SeparableConv2D(num_classes,kernel_size=(2,2), activation = 'relu')) #1X1X10 ,RF=56x56
model.add(Flatten())

model.add(Activation('softmax'))

# Compile the model
#model.compile(optimizer='RMSprop', loss='categorical_crossentropy', metrics=['accuracy'])
model.compile(optimizer='adam', loss='categorical_crossentropy', metrics=['accuracy'])
model.summary()



3.  50 epoch log for new modified code is below : 


Epoch 1/50
195/195 [==============================] - 28s 143ms/step - loss: 1.5429 - acc: 0.4537 - val_loss: 1.5794 - val_acc: 0.4771
Epoch 2/50
195/195 [==============================] - 24s 125ms/step - loss: 1.0520 - acc: 0.6259 - val_loss: 1.0471 - val_acc: 0.6360
Epoch 3/50
195/195 [==============================] - 24s 125ms/step - loss: 0.9099 - acc: 0.6796 - val_loss: 0.8903 - val_acc: 0.6876
Epoch 4/50
195/195 [==============================] - 24s 125ms/step - loss: 0.8211 - acc: 0.7125 - val_loss: 0.9371 - val_acc: 0.6804
Epoch 5/50
195/195 [==============================] - 24s 124ms/step - loss: 0.7550 - acc: 0.7358 - val_loss: 0.8131 - val_acc: 0.7303
Epoch 6/50
195/195 [==============================] - 24s 125ms/step - loss: 0.7041 - acc: 0.7530 - val_loss: 0.7531 - val_acc: 0.7405
Epoch 7/50
195/195 [==============================] - 24s 124ms/step - loss: 0.6678 - acc: 0.7662 - val_loss: 0.6864 - val_acc: 0.7602
Epoch 8/50
195/195 [==============================] - 24s 125ms/step - loss: 0.6352 - acc: 0.7771 - val_loss: 0.7016 - val_acc: 0.7605
Epoch 9/50
195/195 [==============================] - 24s 124ms/step - loss: 0.6063 - acc: 0.7889 - val_loss: 0.7018 - val_acc: 0.7637
Epoch 10/50
195/195 [==============================] - 24s 125ms/step - loss: 0.5795 - acc: 0.7960 - val_loss: 0.6345 - val_acc: 0.7834
Epoch 11/50
195/195 [==============================] - 24s 125ms/step - loss: 0.5583 - acc: 0.8033 - val_loss: 0.7148 - val_acc: 0.7623
Epoch 12/50
195/195 [==============================] - 24s 125ms/step - loss: 0.5371 - acc: 0.8117 - val_loss: 0.6885 - val_acc: 0.7705
Epoch 13/50
195/195 [==============================] - 24s 125ms/step - loss: 0.5257 - acc: 0.8155 - val_loss: 0.6300 - val_acc: 0.7904
Epoch 14/50
195/195 [==============================] - 24s 125ms/step - loss: 0.5041 - acc: 0.8217 - val_loss: 0.6357 - val_acc: 0.7869
Epoch 15/50
195/195 [==============================] - 24s 125ms/step - loss: 0.4889 - acc: 0.8298 - val_loss: 0.6401 - val_acc: 0.7949
Epoch 16/50
195/195 [==============================] - 24s 124ms/step - loss: 0.4805 - acc: 0.8305 - val_loss: 0.6016 - val_acc: 0.7981
Epoch 17/50
195/195 [==============================] - 24s 124ms/step - loss: 0.4662 - acc: 0.8338 - val_loss: 0.6240 - val_acc: 0.7942
Epoch 18/50
195/195 [==============================] - 24s 125ms/step - loss: 0.4517 - acc: 0.8403 - val_loss: 0.5973 - val_acc: 0.8054
Epoch 19/50
195/195 [==============================] - 24s 125ms/step - loss: 0.4445 - acc: 0.8426 - val_loss: 0.6148 - val_acc: 0.8011
Epoch 20/50
195/195 [==============================] - 24s 125ms/step - loss: 0.4329 - acc: 0.8455 - val_loss: 0.5991 - val_acc: 0.8064
Epoch 21/50
195/195 [==============================] - 24s 125ms/step - loss: 0.4222 - acc: 0.8493 - val_loss: 0.5964 - val_acc: 0.8077
Epoch 22/50
195/195 [==============================] - 24s 125ms/step - loss: 0.4128 - acc: 0.8545 - val_loss: 0.5832 - val_acc: 0.8166
Epoch 23/50
195/195 [==============================] - 24s 125ms/step - loss: 0.4018 - acc: 0.8583 - val_loss: 0.6473 - val_acc: 0.7968
Epoch 24/50
195/195 [==============================] - 24s 125ms/step - loss: 0.3903 - acc: 0.8618 - val_loss: 0.5916 - val_acc: 0.8096
Epoch 25/50
195/195 [==============================] - 24s 124ms/step - loss: 0.3835 - acc: 0.8670 - val_loss: 0.5708 - val_acc: 0.8184
Epoch 26/50
195/195 [==============================] - 24s 125ms/step - loss: 0.3790 - acc: 0.8652 - val_loss: 0.5690 - val_acc: 0.8205
Epoch 27/50
195/195 [==============================] - 24s 125ms/step - loss: 0.3714 - acc: 0.8665 - val_loss: 0.6109 - val_acc: 0.8122
Epoch 28/50
195/195 [==============================] - 24s 124ms/step - loss: 0.3614 - acc: 0.8703 - val_loss: 0.5994 - val_acc: 0.8148
Epoch 29/50
195/195 [==============================] - 24s 124ms/step - loss: 0.3601 - acc: 0.8697 - val_loss: 0.6231 - val_acc: 0.8075
Epoch 30/50
195/195 [==============================] - 24s 125ms/step - loss: 0.3547 - acc: 0.8739 - val_loss: 0.6237 - val_acc: 0.8083
Epoch 31/50
195/195 [==============================] - 24s 125ms/step - loss: 0.3437 - acc: 0.8778 - val_loss: 0.5802 - val_acc: 0.8241
Epoch 32/50
195/195 [==============================] - 24s 125ms/step - loss: 0.3390 - acc: 0.8783 - val_loss: 0.6638 - val_acc: 0.7965
Epoch 33/50
195/195 [==============================] - 24s 124ms/step - loss: 0.3363 - acc: 0.8791 - val_loss: 0.5854 - val_acc: 0.8212
Epoch 34/50
195/195 [==============================] - 24s 125ms/step - loss: 0.3279 - acc: 0.8844 - val_loss: 0.6211 - val_acc: 0.8139
Epoch 35/50
195/195 [==============================] - 24s 125ms/step - loss: 0.3244 - acc: 0.8839 - val_loss: 0.5601 - val_acc: 0.8246
Epoch 36/50
195/195 [==============================] - 24s 125ms/step - loss: 0.3217 - acc: 0.8850 - val_loss: 0.5764 - val_acc: 0.8252
Epoch 37/50
195/195 [==============================] - 24s 125ms/step - loss: 0.3103 - acc: 0.8895 - val_loss: 0.5958 - val_acc: 0.8232
Epoch 38/50
195/195 [==============================] - 24s 125ms/step - loss: 0.3155 - acc: 0.8868 - val_loss: 0.6309 - val_acc: 0.8163
Epoch 39/50
195/195 [==============================] - 24s 125ms/step - loss: 0.3125 - acc: 0.8890 - val_loss: 0.5950 - val_acc: 0.8225
Epoch 40/50
195/195 [==============================] - 24s 125ms/step - loss: 0.3026 - acc: 0.8922 - val_loss: 0.6027 - val_acc: 0.8150
Epoch 41/50
195/195 [==============================] - 24s 124ms/step - loss: 0.2946 - acc: 0.8942 - val_loss: 0.5797 - val_acc: 0.8259
Epoch 42/50
195/195 [==============================] - 24s 125ms/step - loss: 0.2972 - acc: 0.8927 - val_loss: 0.6103 - val_acc: 0.8238
Epoch 43/50
195/195 [==============================] - 24s 124ms/step - loss: 0.2873 - acc: 0.8965 - val_loss: 0.6672 - val_acc: 0.8084
Epoch 44/50
195/195 [==============================] - 24s 124ms/step - loss: 0.2901 - acc: 0.8957 - val_loss: 0.5875 - val_acc: 0.8257
Epoch 45/50
195/195 [==============================] - 24s 124ms/step - loss: 0.2876 - acc: 0.8962 - val_loss: 0.6108 - val_acc: 0.8233
Epoch 46/50
195/195 [==============================] - 24s 125ms/step - loss: 0.2878 - acc: 0.8974 - val_loss: 0.5961 - val_acc: 0.8217
Epoch 47/50
195/195 [==============================] - 24s 124ms/step - loss: 0.2790 - acc: 0.9006 - val_loss: 0.6719 - val_acc: 0.8061
Epoch 48/50
195/195 [==============================] - 24s 124ms/step - loss: 0.2738 - acc: 0.9017 - val_loss: 0.5806 - val_acc: 0.8329
Epoch 49/50
195/195 [==============================] - 24s 125ms/step - loss: 0.2747 - acc: 0.8999 - val_loss: 0.6075 - val_acc: 0.8261
Epoch 50/50
195/195 [==============================] - 24s 125ms/step - loss: 0.2715 - acc: 0.9019 - val_loss: 0.6003 - val_acc: 0.8224
Model took 1220.95 seconds to train

Accuracy on test data is: 82.24

