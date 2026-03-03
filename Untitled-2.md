	//Quick order
{
  "order_preparation_duration": "01:10:00", 
  "is_deleted": false, 
  "customer":
  {
    "name": "{{customerName}}",
    "contact": "{{customerContactNumber}}", 
    "email": "{{customerEmailAddress}}"
  },
  "order_type": 1, 
   "guest_count": 2,
  "action_type": 3, 
  "order_checks": 
  [
    {
      
      "items": 
      [
        {
          "menu_group": 146,
          "item": 71,
          "qty": 2,
          "split_for": 1, 
          "modifier_groups": 
          [
            {
              "modifier_group": [78,82]
                [
                {
                  "modifier": [776,777,778],
                  "qty": 1
                }
              ]
            }
          ],
          
          "is_sent_to_kitchen": true 
        }
      ]
    }
  ]
}

1 st 
-------------------------------------------------------------------------------------
{
  "order_preparation_duration": "01:10:00",
  "is_deleted": false,
  "customer": {
    "name": "{{customerName}}",
    "contact": "{{customerContactNumber}}",
    "email": "{customerEmailAddress}"
  },
  "order_type": 1,
  "guest_count": 2,
  "action_type": 3,
  "order_checks": [
    {
      "items": [
        {
          "menu_group": 146,
          "item": 71,
          "qty": 2,
          "split_for": 1,
          "modifier_groups": [
            {
              "modifier_group": 78,
              "modifiers": [
                {
                  "modifier": 776,
                  "qty": 1
                }
              ]
            }
          ],
          "is_sent_to_kitchen": true
        }
      ]
    }
  ]
}