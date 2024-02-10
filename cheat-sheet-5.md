# NLP with transformers, quick conda setup

Create a Conda env
``` conda create -n [name of the new env] python=3.11```

Activate your conda env
``` conda activate [name of the new env] ```

Upgrade pip for this new env
``` pip install --upgrade pip```

Install transformers library (we us it a lot)
``` pip install transformers ```

Run Jupyter Lab
``` jupyter-lab```

[About Conda](https://docs.conda.io/en/latest/)

**Update** : Recommanded setup with mamba as package manager: see conda miniforge documentation [here](https://github.com/conda-forge/miniforge#manbaforge) to see how to install. 

Then use **mamba** instead of **conda** 
``` mamba install jupyter```



# Install Excalidraw locally 

[Installation | Excalidraw developer docs](https://docs.excalidraw.com/docs/@excalidraw/excalidraw/installation)

```
git clone https://github.com/excalidraw/excalidraw.git
cd excalidraw
npm install
npm start
```

Go to: http://localhost:3000 


