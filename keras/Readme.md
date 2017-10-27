Keras Image
===

> Unofficial docker images of Keras for personal uses

See on Docker hub [https://hub.docker.com/r/neungkl/keras/](https://hub.docker.com/r/neungkl/keras/)

# Package Installed

- ipython
- jupyter
- numpy
- scipy
- pandas
- matplotlib
- sklean
- six
- tensorflow
- keras
- h5py

# Usage

```
docker run -it -p 8888:8888 neungkl/keras
```
Go to your browser `http://localhost:8888`

## Mount Directory

```
docker run -it -p 8888:8888 -v <YOUR_PROJECT_DIRECTORY>:/home/work neungkl/keras
```

# License

[MIT](LICENSE) © Kosate Limpongsa
