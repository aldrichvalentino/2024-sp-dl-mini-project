# Steps to Run Jupyter Notebook on HPC

1. Open two terminal sessions
2. SSH to greene cluster as usual
3. Submit the `sbatch` for jupyter, either with CPU or GPU.
4. Wait until the job has been executed and find the slurm out file.
5. Go to the slurm file, you will find something like an ssh with localhost binding:

```sh
ssh -L port:localhost:port netId@greene
```

6. Copy the `-L <binding>` part, you will need this
7. On another terminal, connect to the gateway using the added commands:

```sh
ssh -L <binding> netId@gw...
```

8. One more time, connect to greene with the binding:

```sh
ssh -L <binding> netId@greene
```

9. Last, copy the link from the slurm out file, something like `localhost?token=...` and paste it on a web browser.
