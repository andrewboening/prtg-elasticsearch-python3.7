# prtg-elasticsearch-python3.7
Python script to check Elasticsearch cluster health and return JSON results to PRTG. Script has been updated to support Python 3.7

The paepy module has been dropped so the new imports will need to be used;

## ORIGINAL
from paepy.ChannelDefinition import CustomSensorResult

## UPDATED
from prtg.sensor.result import CustomSensorResult
from prtg.sensor.units import ValueUnit

The channel definition has also changed;

## ORIGINAL
sensor.add_channel(channel_name="Status",unit="Count",value=status,is_limit_mode=True,limit_max_error=1.5,limit_max_warning=0.5)

## UPDATED
sensor.add_channel(name="Status",unit="Count",value=status,is_limit_mode=True,limit_max_error=1.5,limit_max_warning=0.5)

Sending the data back to the sensor, I changed the following;

## ORGINAL
print(sensor.get_json_result())

## UPDATED
print(sensor)
