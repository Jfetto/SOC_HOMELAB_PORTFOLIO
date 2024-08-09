When having a reverse shell opened via sliver on a vulnerable host that is being monitored by LC, if you rename the implant while it is still active, LC does not notice this change and still kicks out events with the past exe name. The file does change in the filesystem on LC, but not for any events. This happens both in live feed and Timeline

# Screenshots 
## call back from implant Prior to the change 
![image](https://github.com/user-attachments/assets/3285ac02-f7a2-483e-a934-25ceb53458c3)
![image](https://github.com/user-attachments/assets/64b64f16-6dfb-4e26-9033-fc22a4b73c8c)

## call back from implant after change 

![image](https://github.com/user-attachments/assets/4281041d-5908-452d-8668-6a0384202628)

![image](https://github.com/user-attachments/assets/de229a10-b189-4ebe-a949-66b2fd067e16)
![image](https://github.com/user-attachments/assets/14748593-3be5-46a8-adb6-91e86501eacc)
![image](https://github.com/user-attachments/assets/b4b99ebf-3020-423f-8146-e8b9b7a399b9)



#Events
## call back from implant Prior to the change 
```
{
  "event": {
    "COMMAND_LINE": "\"C:\\Users\\admin\\Downloads\\notabug.exe\" ",
    "FILE_IS_SIGNED": 0,
    "FILE_PATH": "C:\\Users\\admin\\Downloads\\notabug.exe",
    "HASH": "42ab26a895bc25552852461a6b81f60600f028001b5b2f807938df74d5986cdb",
    "NETWORK_ACTIVITY": [
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58291
        },
        "TIMESTAMP": 1723178750598
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58292
        },
        "TIMESTAMP": 1723178752047
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58293
        },
        "TIMESTAMP": 1723178754957
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58294
        },
        "TIMESTAMP": 1723178756491
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58295
        },
        "TIMESTAMP": 1723178758957
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58296
        },
        "TIMESTAMP": 1723178761470
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58297
        },
        "TIMESTAMP": 1723178763618
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58298
        },
        "TIMESTAMP": 1723178766223
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58299
        },
        "TIMESTAMP": 1723178768611
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58300
        },
        "TIMESTAMP": 1723178773458
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58301
        },
        "TIMESTAMP": 1723178776144
      }
    ],
    "PARENT_PROCESS_ID": 3716,
    "PROCESS_ID": 5152,
    "USER_NAME": "VULNWIN\\admin"
  },
  "routing": {
    "arch": 2,
    "did": "",
    "event_id": "877d1edb-520f-41df-8307-01e9fbc27f78",
    "event_time": 1723178778446,
    "event_type": "NETWORK_CONNECTIONS",
    "ext_ip": "207.255.16.128",
    "hostname": "vulnwin.ht.home",
    "iid": "2db4694d-444c-4046-aff7-5166767ec017",
    "int_ip": "192.168.40.77",
    "moduleid": 2,
    "oid": "a03657ed-3537-414c-a82c-fbcd31cc8841",
    "parent": "53941de42d317f1547cad13466b59e6b",
    "plat": 268435456,
    "sid": "0d47638f-66e1-4839-ae72-8aecb77bf710",
    "tags": [],
    "this": "3eb3ae1d48d1835932ad854d66b59f1a"
  },
  "ts": "2024-08-09 04:46:18"
}

```

## call back from implant after change
```
{
  "event": {
    "COMMAND_LINE": "\"C:\\Users\\admin\\Downloads\\notabug.exe\" ",
    "FILE_IS_SIGNED": 0,
    "FILE_PATH": "C:\\Users\\admin\\Downloads\\notabug.exe",
    "HASH": "42ab26a895bc25552852461a6b81f60600f028001b5b2f807938df74d5986cdb",
    "NETWORK_ACTIVITY": [
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58490
        },
        "TIMESTAMP": 1723179213040
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58491
        },
        "TIMESTAMP": 1723179214294
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58492
        },
        "TIMESTAMP": 1723179215356
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58493
        },
        "TIMESTAMP": 1723179216698
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58494
        },
        "TIMESTAMP": 1723179218218
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58495
        },
        "TIMESTAMP": 1723179220822
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58496
        },
        "TIMESTAMP": 1723179223482
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58497
        },
        "TIMESTAMP": 1723179225504
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58498
        },
        "TIMESTAMP": 1723179226529
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58499
        },
        "TIMESTAMP": 1723179228546
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58500
        },
        "TIMESTAMP": 1723179231348
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58501
        },
        "TIMESTAMP": 1723179233947
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58502
        },
        "TIMESTAMP": 1723179235865
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58503
        },
        "TIMESTAMP": 1723179237518
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58504
        },
        "TIMESTAMP": 1723179240354
      },
      {
        "DESTINATION": {
          "IP_ADDRESS": "192.168.40.65",
          "PORT": 80
        },
        "IS_OUTGOING": 1,
        "PROTOCOL": "tcp4",
        "SOURCE": {
          "IP_ADDRESS": "192.168.40.77",
          "PORT": 58505
        },
        "TIMESTAMP": 1723179241817
      }
    ],
    "PARENT_PROCESS_ID": 3716,
    "PROCESS_ID": 5152,
    "USER_NAME": "VULNWIN\\admin"
  },
  "routing": {
    "arch": 2,
    "did": "",
    "event_id": "ed89a071-975b-4f91-b936-4018098792fe",
    "event_time": 1723179243375,
    "event_type": "NETWORK_CONNECTIONS",
    "ext_ip": "207.255.16.128",
    "hostname": "vulnwin.ht.home",
    "iid": "2db4694d-444c-4046-aff7-5166767ec017",
    "int_ip": "192.168.40.77",
    "moduleid": 2,
    "oid": "a03657ed-3537-414c-a82c-fbcd31cc8841",
    "parent": "53941de42d317f1547cad13466b59e6b",
    "plat": 268435456,
    "sid": "0d47638f-66e1-4839-ae72-8aecb77bf710",
    "tags": [],
    "this": "92149dca5ed4d651dad1d53a66b5a0eb"
  },
  "ts": "2024-08-09 04:54:03"
}

```






![image](https://github.com/user-attachments/assets/64b64f16-6dfb-4e26-9033-fc22a4b73c8c)
