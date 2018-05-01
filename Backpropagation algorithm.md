

```python
import numpy as np
X=np.array([[1,0,1,0],[1,0,1,1],[0,1,0,1]])
Wh=np.array([[.42,.88,.55],[.10,.73,.68],[.60,.18,.47],[.92,.11,.52]])
Bh=np.array([.46,.72,.08])
Hidden_layer_input=np.zeros(shape=(3,3))
Hidden_Activation_layer=np.zeros(shape=(3,3))
Wout=np.array([[.30],[.25],[.23]])
bout=np.array([.69])
Output=np.array([[1],[2],[3]])
Y=np.array([1,1,0])
E=np.zeros(shape=(1,3))
Slope_hidden_layer=np.zeros(shape=(3,3))
Slope_Output_layer=np.zeros(shape=(1,3))
Delta_output=np.zeros(shape=(1,3))
Error_at_hidden_layer=np.zeros(shape=(3,3))
Delta_hidden_layer=np.zeros(shape=(3*3))
Learning_rate=np.array([.1])
NewX=np.empty([4,3])

for i in range(len(X)):
     for W in range(len(Wh[0])):
         Hidden_layer_input[i][W]=sum(X[i]*Wh[:,W])+Bh[W]
         Hidden_Activation_layer[i][W]=1/(1+np.exp(-Hidden_layer_input[i][W]))
         Output=sum(Hidden_Activation_layer*Wout)+bout
         Output=1/(1+np.exp(-Output))
         E=Y-Output
         Slope_hidden_layer=(Hidden_Activation_layer)*(1-Hidden_Activation_layer)
         Slope_Output_layer=(Output)*(1-Output)
         Delta_output=E*Slope_Output_layer
         Error_at_hidden_layer=np.transpose(Delta_output*Wout)
         Delta_hidden_layer=Error_at_hidden_layer*Slope_hidden_layer
         Hidden_Activation_layer=np.transpose(Hidden_Activation_layer)
         We=sum(Hidden_Activation_layer*Wout)
         Wout=np.transpose(Wout)
         Wout=Wout+(We*Learning_rate)
         NewX=np.transpose(X)


for Z in range(len(NewX[0])):
     for S in range(len(Delta_hidden_layer[0])):
          NewX[Z][S]=sum(NewX[Z]*Delta_hidden_layer[:,Z])
          Wh=Wh+(NewX*Learning_rate)
          Vh=Bh.reshape(3,1)
          Bh=Bh+(Bh.sum(axis=0)*Learning_rate)
          bout=bout+(Delta_output.sum(axis=0)*Learning_rate)
         
        
print("Hiddenlayer is",Hidden_layer_input)
print("Hidden activation layer is",Hidden_Activation_layer)
print("Output is",Output)
print("Error is",E)
print("Slope at hidden layer is",Slope_hidden_layer)
print("Slope at output layer is",Slope_Output_layer)
print("Delta output is",Delta_output)
print("Error at hidden layer is",Error_at_hidden_layer)
print("Delta hidden layer is",Delta_hidden_layer)
print("Updated Wout is",Wout)
print("Updated Wh value is",Wh)
print("Updated value of Bh",Bh)
print("Updated value of bout",bout)
```

    Hiddenlayer is [[1.48 1.78 1.1 ]
     [2.4  1.89 1.62]
     [1.48 1.56 1.28]]
    Hidden activation layer is [[0.81457258 0.85569687 0.81457258]
     [0.9168273  0.86875553 0.83479513]
     [0.75026011 0.82635335 0.78244978]]
    Output is [0.9433392  0.93301776 0.8852289 ]
    Error is [ 0.0566608   0.06698224 -0.8852289 ]
    Slope at hidden layer is [[0.15104409 0.076255   0.18736988]
     [0.12347974 0.11401936 0.14349349]
     [0.15104409 0.13791222 0.17022212]]
    Slope at output layer is [0.05345035 0.06249562 0.10159869]
    Delta output is [ 0.00302854  0.0041861  -0.0899381 ]
    Error at hidden layer is [[ 0.00309558  0.00252746  0.00214012]
     [ 0.00378665  0.00300137  0.00246599]
     [-0.0668999  -0.05002831 -0.03852573]]
    Delta hidden layer is [[ 0.00046757  0.00019273  0.00040099]
     [ 0.00046757  0.00034221  0.00035385]
     [-0.01010484 -0.00689952 -0.00655793]]
    Updated Wout is [[1.23492885 1.02291907 0.8471961 ]
     [1.11736821 0.90535843 0.72963545]
     [0.95663517 0.74462538 0.56890241]]
    Updated Wh value is [[0.42 0.98 0.55]
     [0.1  0.73 1.18]
     [1.2  0.88 0.47]
     [0.92 1.01 1.42]]
    Updated value of Bh [4.49388974 4.75388974 4.11388974]
    Updated value of bout [0.61554888]
    
