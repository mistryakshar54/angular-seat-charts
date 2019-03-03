# Seat-Chart-Generator

Seat-Chart-Generator is a seat chart app made in Angular 6, an inspiration from  [jQuery Seat Charts](https://github.com/mateuszmarkowski/jQuery-Seat-Charts)

## Demo Link
[Stackblitz Demo Link](https://angular-yw5azm.stackblitz.io)

## Dependencies 
[Bootstrap](https://getbootstrap.com/) \
[Ngx-bootstrap](https://valor-software.com/ngx-bootstrap)

## Basic Setup Example
### **Generating the seats**

```

//Sample JSON for seatConfig
    [
      {
        "seat_price": 250,
        "seat_map": [
          {
            "seat_label": "1",
            "layout": "g_____"
          },
          {
            "seat_label": "2",
            "layout": "gg__gg"
          },
          {
            "seat_label": "3",
            "layout": "gg__gg"
          }
        ]
      },
      {
        "seat_price": 450,
        "seat_map": [
          {
            "seat_label": "4",
            "layout": "g_____"
          },
          {
            "seat_label": "5",
            "layout": "gg__gg"
          },
          {
            "seat_label": "6",
            "layout": "gg__gg"
          }
        ]
      }
    ]    
```

### **"seat_map" : []**
The array that contains the "seat_label" for each row and the corresponding layout for that row is defined in the "layout" property.

### **"layout" : "gg__gg"**

A seat is defined using 'g' and a space is defined using '_' character in the layout property. 

### **"seat_price" : 450**

Defines the price for each "seat_map[]".


## **Map Customizations**

```
seatChartConfig = {
    showRowsLabel : false,
    showRowWisePricing : false,
    newSeatNoForRow : false
  }
```

### seatChartConfig 


JSON which manages the basic settings of the map.

**showRowsLabel** : Boolean variable to check if we want to display the Label for the row.
  
**showRowWisePricing**: Boolean variable to display price after each seat map block.

**newSeatNoForRow**: Continue the seat no for the next row.

## **Generate the seat layout**
Pass the configured **seatConfig** JSON to the processSeatChart() function.
```
this.seatConfig = [
      {
        "seat_price": 250,
        "seat_map": [
          {
            "seat_label": "1",
            "layout": "g_____"
          },
          {
            "seat_label": "2",
            "layout": "gg__gg"
          }
        ]
      }
    ];    
    this.processSeatChart(this.seatConfig);
```
 
## **Block Seats**
Want to block seats beforehand?
Pass in a string of seat-ids to block to the blockSeats() function.
```
    this.blockSeats("7_1,7_2");
```

## **Seat Color Customizations**
Don't like the seat colors? No worries!\
Go to app.component.scss file and edit the below SASS variables according to your favorite color
```
$seat-available-bg: white;
$seat-available-color: #a0a0a0;
$seat-booked-bg: #a0a0a0;
$seat-booked-color: white;
$seat-unavailable-bg: black;
$seat-unavailable-color: white;
```


## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License
[MIT](https://choosealicense.com/licenses/mit/)