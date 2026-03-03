{
  "reservation": {{reservationID}}, 
  "order_preparation_duration": "12:56:10",
  "order_table_status": 2, 
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
          "menu_group": 0,
          "item": 0,
          "size": 0, // Optional based on the selected items config
          "qty": 0,
          "split_for": 5, //default 1, and then 2 to 5 values
          "modifier_groups": //modifier_groups is optional, it may be 1 object or multiple that means multiple-modifier_groups in the same item
          [
            {
              "modifier_group": 0,
              "modifiers": //modifiers is required if modifier_groups is there, it may be 1 object or multiple that means multiple-modifiers in the same modifier_groups
              [
                {
                  "modifier": 0,
                  "qty": 0
                }
              ]
            }
          ],
          "discount": //this object is optional but if this is present then it cannot be applied in the same check (it can be applied in another check of the same order)
          {
            "discount_type": 1, // 1=comp_off, 2=percentage, 3=fixed_amount, 4=promo_code
            "value": 0,
            "promo_code": "string",
            "reason": "string"
          },
          "is_sent_to_kitchen": true // This is used to hold particular item, this will be used in combination with the "action_type"
        }
      ]
    }
  ]
}