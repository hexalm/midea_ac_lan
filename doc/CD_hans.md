# 空气能热水器

## 特性
- 支持温度设定

设置温度调整步长 (默认为1).

```
{"temperature_step": 0.5}
```

## 生成实体
### 默认生成实体
| 实体ID                                 | 类型           | 描述    |
|--------------------------------------|--------------|-------|
| water_heater.{DEVICEID}_water_heater | water_heater | 热水器实体 |

### Extra entities

| EntityID                                     | 类型                | 名称                     | 描述    |
|----------------------------------------------|-------------------|------------------------|-------|
| sensor.{DEVICEID}_compressor_temperature     | sensor            | Compressor Temperature | 压缩机温度 |
| sensor.{DEVICEID}_condenser_temperature      | sensor            | Condenser Temperature  | 冷凝器温度 |
| sensor.{DEVICEID}_outdoor_temperature        | sensor            | Outdoor Temperature    | 室外温度  |
| binary_sensor.{DEVICEID}_outdoor_temperature | compressor_status | Compressor Status      | 压缩机状态 |
| switch.{DEVICEID}_power                      | switch            | Power                  | 电源    |
| switch.{DEVICEID}_aux_heating                | switch            | Aux Heating            | 电辅热   |

## 服务
生成以下扩展服务

### midea_ac_lan.set_attribute

[![Service](https://my.home-assistant.io/badges/developer_call_service.svg)](https://my.home-assistant.io/redirect/developer_call_service/?service=midea_ac_lan.set_attribute)

设置设备属性, 服务数据:

| 名称        | 描述                        |
|-----------|---------------------------|
| device_id | 设备的编号(Device ID)          |
| attribute | "power"</br>"aux_heating" |
| value     | true 或 false              |

示例
```
service: midea_ac_lan.set_attribute
data:
  device_id: XXXXXXXXXXXX
  attribute: power
  value: false
```