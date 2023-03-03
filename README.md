# WP1.1-Feature-Digital-Concept
Scripted/Completed open to feedback
import tensorflow as tf

import matplotlib.pyplot as plt

# define the model parameters
wing_span = tf.Variable(30, name='wing_span')
wing_chord = tf.Variable(4, name='wing_chord')
wing_thickness = tf.Variable(0.5, name='wing_thickness')

# define the model
def blended_wing_model(wing_span, wing_chord, wing_thickness):
  return (wing_span*wing_chord*wing_thickness)

# define the loss function
def loss_function(predicted_wing_area, actual_wing_area):
  return tf.abs(predicted_wing_area - actual_wing_area)

# define the optimizer
optimizer = tf.keras.optimizers.Adam(learning_rate=0.01)

# define the training loop
def train(wing_span, wing_chord, wing_thickness, actual_wing_area):
  with tf.GradientT

ape() as tape:
    predicted_wing_area = blended_wing_model(wing_span, wing_chord, wing_thickness)
    loss_value = loss_function(predicted_wing_area, actual_wing_area)
    gradients = tape.gradient(loss_value, [wing_span, wing_chord, wing_thickness])
  optimizer.apply_gradients(zip(gradients, [wing_span, wing_chord, wing_thickness]))

# Run the training loop
for i in range(1000):
  train(wing_span, wing_chord, wing_thickness, 120)
  if i % 100 == 0:
    print("Loss at step {:03d}: {:.3f}".format(i, loss_value))

# Print the final results
print("Final loss: {:.3f}".format(loss_value))
print("Wing span: {:.3f}".format(wing_span.numpy()))
print("Wing chord: {:.3f}".format(wing_chord.



