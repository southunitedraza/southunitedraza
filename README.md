def process_paymentout(card_number, expiry_date, cvv):


    # Validate input 


    if not is_valid_card_number(card_number):


        return "Invalid card number"





    # Encrypt sensitive data


    encrypted_card_number = encrypt(card_number)


    


    # Send payment request to gateway


    response = payment_gateway.charge(encrypted_card_number, expiry_date, cvv, amount)





    if response.success:


        # Update user account


        update_user_payment_status(user_id, "paid")


        return "Payment successful"


    else:


        return "Payment failed"
