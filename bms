class BatteryManagementSystem:
    def __init__(self, initial_level):
        self.battery_level = initial_level
        self.MAX_BATTERY_CAPACITY = 100  # Battery capacity in percentage
        self.SOLAR_CHARGE_RATE = 10      # Solar charge rate per cycle
        self.LOAD_DISCHARGE_RATE = 5     # Load discharge rate per cycle

    def charge_battery(self):
        if self.battery_level < self.MAX_BATTERY_CAPACITY:
            self.battery_level += self.SOLAR_CHARGE_RATE
            if self.battery_level > self.MAX_BATTERY_CAPACITY:
                self.battery_level = self.MAX_BATTERY_CAPACITY
            print(f"Battery charging... Current level: {self.battery_level}%")
        else:
            print("Battery fully charged.")

    def discharge_battery(self):
        if self.battery_level > 0:
            self.battery_level -= self.LOAD_DISCHARGE_RATE
            if self.battery_level < 0:
                self.battery_level = 0
            print(f"Battery discharging... Current level: {self.battery_level}%")
        else:
            print("Battery empty.")

class AutomaticTransferSwitch:
    def __init__(self):
        self.using_solar = True
        self.MIN_BATTERY_CAPACITY = 20  # Minimum battery capacity before switching to grid

    def check_and_switch(self, bms):
        if bms.battery_level <= self.MIN_BATTERY_CAPACITY:
            self.using_solar = False
            print("Switching to grid power...")
        elif bms.battery_level > self.MIN_BATTERY_CAPACITY:
            self.using_solar = True
            print("Switching to solar power...")

def main():
    # Initialize BMS with 50% battery level
    bms = BatteryManagementSystem(50)
    ats = AutomaticTransferSwitch()

    for i in range(20):
        if ats.using_solar:
            bms.charge_battery()
        else:
            bms.discharge_battery()
        ats.check_and_switch(bms)

if __name__ == "__main__":
    main()
