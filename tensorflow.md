### AUC metric in Estimator 
estimation of the metric over a stream of data
``` tf.compat.v1.metrics.auc ```
instead of 
``` tf.keras.metrics.AUC() ```


### Adaptive padding
```python
train_padded = train.padded_batch(batch_size=BATCH_SIZE, 
                                  padded_shapes=([-1], []))
```

first element in ```padded_shapes``` is given -1 or None to pad to the smallest per-batch size that fits all elements
second element is padded to the smallest size that fits
v.s. fixed padding

```python
train = train.padded_batch(batch_size=BATCH_SIZE, padded_shapes=([256], []))
```


### Tensorflow Serving
```shell
docker run -d --name serving_base tensorflow/serving
docker cp /Users/ming/DS/netflights-propensity-model/saved_model/netflights/v1 serving_base:/models/netflightsPropensity
docker commit --change "ENV MODEL_NAME netflightsPropensity" serving_base ming/netflights_serving:v1
docker kill serving_base
docker rm serving_base
docker run -p 8500:8500 -t ming/netflights_serving:v1 &
```