# Philips_July_2022
Assigment


//Python
def battery_is_ok(temperature, soc, charge_rate):
  if temperature < 0 or temperature > 45:
    print('Temperature is out of range!')
    return False
  elif soc < 20 or soc > 80:
    print('State of Charge is out of range!')
    return False
  elif charge_rate > 0.8:
    print('Charge rate is out of range!')
    return False

  return True
  
  
  Above Code has a following voilation:
    1. SRP==> because battery_is_ok handles 3 Responsblity such as  temperature, SOC, Change_rate
    2. the above resposblity may be subdivided into 3 diffrent methods.
    
 # Refactored code
 
 def battery_is_ok(temperature, soc, charge_rate):
  

  return temperature_is_ok(temperature) and soc_is_ok(soc) and charge_rate_is_ok(charge_rate)
  
  
  def temperature_is_ok(temperature):
    if temperature < 0 or temperature > 45:
      return False
    return True
    
    
 def soc_is_ok(soc):
    if soc < 20 or soc > 80:
      return False
    return True
    
  def charge_rate_is_ok(charge_rate):
    if charge_rate > 0.8:
      return False
    return True
