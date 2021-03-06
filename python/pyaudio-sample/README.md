```
pip install pyaudio
```

on ubuntu, one should install portaudio library

```bash
apt-get install portaudio19-dev
```

### for windows user

check the device name with

```
python device.py
```

and replace INPUT_DEVICE and OUTPUT_DEVICE with index of device

```python
stream = pa.open(input_device_index=INPUT_DEVICE,
                 output_device_index=OUTPUT_DEVICE,
                 format=pa.get_format_from_width(WIDTH),
```

for example, on my machine:

```
cmd> python device.py
{'defaultSampleRate': 44100.0, 'defaultLowOutputLatency': 0.09, 'defaultLowInputLatency': 0.09, 'maxInputChannels': 2L, 'structVersion': 2L, 'hostApi': 0L, 'index': 0, 'defaultHighOutputLatency': 0.18, 'maxOutputChannels': 0L, 'name': u'Microsoft Sound Mapper - Input', 'defaultHighInputLatency': 0.18}
{'defaultSampleRate': 44100.0, 'defaultLowOutputLatency': 0.09, 'defaultLowInputLatency': 0.09, 'maxInputChannels': 2L, 'structVersion': 2L, 'hostApi': 0L, 'index': 1, 'defaultHighOutputLatency': 0.18, 'maxOutputChannels': 0L, 'name': u'Microphone (High Definition Aud', 'defaultHighInputLatency': 0.18}
{'defaultSampleRate': 44100.0, 'defaultLowOutputLatency': 0.09, 'defaultLowInputLatency': 0.09, 'maxInputChannels': 0L, 'structVersion': 2L, 'hostApi': 0L, 'index': 2, 'defaultHighOutputLatency': 0.18, 'maxOutputChannels': 2L, 'name': u'Microsoft Sound Mapper - Output', 'defaultHighInputLatency': 0.18}
{'defaultSampleRate': 44100.0, 'defaultLowOutputLatency': 0.09, 'defaultLowInputLatency': 0.09, 'maxInputChannels': 0L, 'structVersion': 2L, 'hostApi': 0L, 'index': 3, 'defaultHighOutputLatency': 0.18, 'maxOutputChannels': 2L, 'name': u'Headphones (High Definition Aud', 'defaultHighInputLatency': 0.18}
```

I would like to do:

```python
stream = pa.open(input_device_index=0,
                 output_device_index=2,
                 format=pa.get_format_from_width(WIDTH),
```
