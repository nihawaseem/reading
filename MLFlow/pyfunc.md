### Flavors
- pyfunc (python function) enables us to encapsulate models from any framework into an mlflow model
- offers a consistent API for deployment 

### How pyfunc works
![[Pasted image 20250630134532.png]]

1. mlflow.pyfunc.load_model() : indicates the intention to load a custom pyfunc model to use
2. system fetches MLmodel config file associated with the saved model
3. artificact mapping : saved model [[artifacts]] are mapped
4. python model initialises 
5. loads context
6. model is ready for inference 