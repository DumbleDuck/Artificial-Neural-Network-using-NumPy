# Artificial Neural Network using NumPy

### Description: 
This model uses basic Python libraries to generate an Artificial Neural Network. It is a great project for beginners who want to dabble in the world of deep learning. To demonstrate the working of this model, it has been trained on the [MNIST dataset](https://www.kaggle.com/competitions/digit-recognizer/data) to recognize handwritten digits and can achieve an accuracy greater than 97%. 

![image](https://user-images.githubusercontent.com/103637312/177565838-d48f2c18-5ee2-43c9-b7ee-abff22ef096c.png)


### Salient Features:
- Layers of the network aren't hardcoded and hence can be customized according to the required application. 
- Implements L2 regularization to prevent overfitting on training set.
- Model uses mini-batch gradient descent for shorter training time and faster convergence.
---

### Mathematics:
![image](https://user-images.githubusercontent.com/103637312/177567020-e3d6ee3e-4b43-4a69-9afa-cbc5707aea80.png)

---
### Hyperparameters:
- `epochs` 
- `layer_data`
- `mini_batch` : mini-batch size.
- `rate` : learning rate of the model.
- `lamda` : regularization parameter.

### Functions:
- `init_params()` : takes an array containing the size of each layer as input. Initializes the weights(`W1,W2..`) with a random matrix generated from a standard normal distribution and biases(`b1,b2..`) with a null matrix.
- `one_hot()` : encodes categorial data to one-hot vector.
- `sigmoid()`,`relu()`,`softmax()` : evaluates activations corresponding to each function.
- `relu_back()`,`softmax_back()` : calculates dZ from dA based on the activation of the layer.  
- `forward_prop_single()`,`forw_prop()` : forward propagation for one and n layers respectively.
- `cost()` : calculates the cross-entropy loss and cost for softmax regression. 
- `back_prop_single()`,`back_prop()` : backward propagation for one and n layers respectively.
- `upd_params()` : update the weights and biases based on learning `rate` and gradients. 
- `acc()` : calculates accuracy of the model. **Use categorial values instead of one-hot vectors as Y values.**

### Dictionaries:
- `params` : contains weights and biases.
- `grads` : contains gradients of each layer.
- `layer_data` : contains the NN architecture (`layer_data["Dim"]`) and activations(`layer_data["Activs"]`). 
---
### Training with batch vs mini-batch gradient descent:
![image](https://user-images.githubusercontent.com/103637312/177566081-f7e679b7-2270-4d93-b45e-29a720ca438e.png)   

**With batch gradient descent**


![image](https://user-images.githubusercontent.com/103637312/177564586-88040f92-abac-4936-a8e1-1d94dce4755c.png)
  
 **With mini-batch size of 512**

---
### Saving weights:
Last cell contains the code that utilizes Pickle to dump the trained parameters in a .json file. These parameters can later be used while deploying the model. Replace `filename.json` with your desired name to save the weights. A copy of parameters with an accuracy of 97.6% has been included that have been trained with a mini-batch size of 512 over 30 epochs.  
