
1.

Validation Accuracy after 50 epochs for base network : 82.85

Model took 1012.29 seconds to train



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



3.  50 epoch logs is below : 


