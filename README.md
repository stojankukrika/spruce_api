FORMAT: 1A

# API_Spruce

# AppHttpControllersApiAuthController

## Login to system [POST /login]


+ Request (application/json)
    + Body

            {
                "email": "foo@bar.com",
                "password": "bar"
            }

+ Response 200 (application/json)
    + Body

            {
                "token": "token",
                "user": {
                    "id": 4,
                    "first_name": "Teacher",
                    "last_name": "Doe",
                    "email": "teacher@sms.com",
                    "phone_number": "465465415",
                    "user_id": "1",
                    "user_avatar": "image.jpg",
                    "subscription_ends_at": "2015-12-07 09:49:19"
                },
                "role": "user"
            }

+ Response 401 (application/json)
    + Body

            {
                "error": "invalid_credentials"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "could_not_create_token"
            }

# User [/user]
Teacher endpoints, can be accessed only with role "user"

## Get all calendar items [GET /user/calendar]


+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "salesteam": [
                    {
                        "id": 1,
                        "salesteam": "Name of team",
                        "target": "111",
                        "invoice_forecast": "1125",
                        "actual_invoice": "205"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Get all call [GET /user/call]


+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "calls": [
                    {
                        "id": 1,
                        "date": "2015-10-15",
                        "call_summary": "Call summary",
                        "company": "Company",
                        "user": "User"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Post call [POST /user/post_call]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "date": "2015-10-11",
                "call_summary": "call summary",
                "company_id": "1",
                "resp_staff_id": "12"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Edit call [POST /user/edit_call]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "call_id": "1",
                "date": "2015-10-11",
                "call_summary": "call summary",
                "company_id": "1",
                "resp_staff_id": "12"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Delete call [POST /user/delete_call]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "call_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Get all category [GET /user/category]


+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "category": [
                    {
                        "id": 1,
                        "category_name": "Category name"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Post category [POST /user/post_category]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "category_name": "category name"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Edit category [POST /user/edit_category]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "category_id": "1",
                "category_name": "category name"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Delete category [POST /user/delete_category]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "call_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Get all company [GET /user/company]


+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "company": [
                    {
                        "id": 1,
                        "name": "Name",
                        "customer": "customer name",
                        "phone": "634654165456"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Post company [POST /user/post_company]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "name": "Company name",
                "email": "email@email.com"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Edit company [POST /user/edit_company]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "company_id": "1",
                "name": "Company name",
                "email": "email@email.com"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Delete company [POST /user/delete_company]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "company_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Get all contract [GET /user/contract]


+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "company": [
                    {
                        "id": 1,
                        "start_date": "2015-11-12",
                        "description": "Description",
                        "name": "Company name",
                        "user": "User name"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Post contract [POST /user/post_contract]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "start_date": "2015-11-11",
                "end_date": "2015-11-11",
                "description": "Description"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Edit contract [POST /user/edit_contract]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "company_id": "1",
                "name": "Company name",
                "email": "email@email.com"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Delete contract [POST /user/delete_contract]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "company_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Get all customer [GET /user/customer]


+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "calls": [
                    {
                        "id": 1,
                        "full_namae": "full namae",
                        "email": "email@email.com",
                        "created_at": "2015--11-11"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Post customer [POST /user/post_customer]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "first_name": "first name",
                "last_name": "last name",
                "email": "email@email.com",
                "password": "password"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Edit customer [POST /user/edit_customer]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "customer_id": "1",
                "first_name": "first name",
                "last_name": "last name",
                "email": "email@email.com",
                "password": "password"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Delete customer [POST /user/delete_customer]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "customer_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Get all invoice [GET /user/invoice]


+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "invoices": [
                    {
                        "id": 1,
                        "invoice_number": "1465456",
                        "invoice_date": "2015-11-11",
                        "customer": "Customer Name",
                        "unpaid_amount": "15.2",
                        "status": "Status",
                        "due_date": "2015-11-11",
                        "invoice_reminder_days": "5"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Post invoice [POST /user/post_invoice]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "invoice_id": "56456",
                "payment_date": "2015-11-11",
                "payment_method": "method",
                "payment_received": "152.2"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Edit invoice [POST /user/edit_invoice]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "invoice_id": "1",
                "customer_id": "5",
                "invoice_date": "2015-11-11",
                "due_date": "2015-11-11",
                "payment_term": "payment_term",
                "status": "status"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Delete invoice [POST /user/delete_invoice]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "invoice_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Get all invoice_payment [GET /user/invoice]


+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "invoices": [
                    {
                        "id": 1,
                        "payment_received": "1525.26",
                        "invoice_number": "15165",
                        "customer": "Customer Name",
                        "person": "Person Name"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Get all leads [GET /user/lead]


+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "salesteam": [
                    {
                        "id": 1,
                        "register_time": "2015-12-22",
                        "opportunity": "1.2",
                        "contact_name": "Contact name",
                        "email": "dsad@asd.com",
                        "phone": "456469465",
                        "salesteam": "Test team"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Post lead [POST /user/post_lead]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "opportunity": "125.5",
                "email": "test@test.com",
                "customer": "12",
                "sales_team_id": "1",
                "tags": "Softwae",
                "country_id": "15"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Edit lead [POST /user/edit_lead]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "lead_id": 1,
                "opportunity": "125.5",
                "email": "test@test.com",
                "customer": "12",
                "sales_team_id": "1",
                "tags": "Softwae",
                "country_id": "15"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Delete lead [POST /user/delete_lead]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "lead_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Get all meeting [GET /user/meeting]


+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "salesteam": [
                    {
                        "id": 1,
                        "meeting_subject": "meeting subject",
                        "starting_date": "2015-12-22",
                        "ending_date": "2015-12-22",
                        "responsible": "User name"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Post meeting [POST /user/post_meeting]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "meeting_subject": "Subject",
                "starting_date": "2015-11-11",
                "ending_date": "2015-11-11"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Edit meeting [POST /user/edit_meeting]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "meeting_id": 1,
                "meeting_subject": "Subject",
                "starting_date": "2015-11-11",
                "ending_date": "2015-11-11"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Delete meeting [POST /user/delete_meeting]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "meeting_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Get all opportunity [GET /user/opportunity]


+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "salesteam": [
                    {
                        "id": 1,
                        "opportunity": "Opportunity",
                        "company": "Company",
                        "next_action": "2015-12-22",
                        "stages": "Stages",
                        "expected_revenue": "Expected revenue",
                        "probability": "probability",
                        "salesteam": "salesteam",
                        "calls": "5",
                        "meetings": "5"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Post opportunity [POST /user/post_opportunity]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "opportunity": "Opportunity",
                "email": "email@email.com",
                "customer": "1",
                "sales_team_id": "1",
                "next_action": "2015-11-11",
                "expected_closing": "2015-11-11"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Edit opportunity [POST /user/edit_opportunity]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "opportunity_id": 1,
                "opportunity": "Opportunity",
                "email": "email@email.com",
                "customer": "1",
                "sales_team_id": "1",
                "next_action": "2015-11-11",
                "expected_closing": "2015-11-11"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Delete opportunity [POST /user/delete_opportunity]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "opportunity_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Get all price_list [GET /user/price_list]


+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "salesteam": [
                    {
                        "id": 1,
                        "pricelist_name": "Price list",
                        "pricelist_status": "1"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Post price list [POST /user/post_price_list]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "pricelist_name": "Price list",
                "pricelist_status": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Edit price list [POST /user/edit_price_list]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "pricelist_id": 1,
                "pricelist_name": "Price list",
                "pricelist_status": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Delete price_list [POST /user/delete_price_list]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "pricelist_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Get all price list version [GET /user/price_list_version]


+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "$pricelist_versions": [
                    {
                        "id": 1,
                        "version_name": "Version",
                        "pricelist_name": "Name",
                        "start_date": "2015-12-22",
                        "end_date": "2015-12-22"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Post price list version [POST /user/post_price_list_version]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "pricelist_version_name": "Version name",
                "pricelist_id": "1",
                "start_date": "2015-11-11",
                "end_date": "2015-11-11"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Edit price list version [POST /user/edit_price_list_version]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "price_list_version_id": 1,
                "pricelist_version_name": "Version name",
                "pricelist_id": "1",
                "start_date": "2015-11-11",
                "end_date": "2015-11-11"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Delete price list version [POST /user/delete_price_list_version]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "price_list_version_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Get all product [GET /user/product]


+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "products": [
                    {
                        "id": 1,
                        "product_name": "product name",
                        "category_name": "category",
                        "product_type": "Type",
                        "status": "1",
                        "quantity_on_hand": "12",
                        "quantity_available": "52"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Post product [POST /user/post_product]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "product_name": "product name",
                "sale_price": "15.2",
                "description": "sadsadsd",
                "quantity_on_hand": "12",
                "quantity_available": "11"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Edit product [POST /user/edit_product]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "product_id": "1",
                "product_name": "product name",
                "sale_price": "15.2",
                "description": "sadsadsd",
                "quantity_on_hand": "12",
                "quantity_available": "11"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Delete product [POST /user/delete_product]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "product_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Get all qtemplate [GET /user/qtemplate]


+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "qtemplates": [
                    {
                        "id": 1,
                        "quotation_template": "product name",
                        "quotation_duration": "10"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Post qtemplate [POST /user/post_qtemplate]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "product_name": "product name",
                "sale_price": "15.2",
                "description": "sadsadsd",
                "quantity_on_hand": "12",
                "quantity_available": "11"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Edit qtemplate [POST /user/edit_qtemplate]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "qtemplate_id": "1",
                "product_name": "product name",
                "sale_price": "15.2",
                "description": "sadsadsd",
                "quantity_on_hand": "12",
                "quantity_available": "11"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Delete qtemplate [POST /user/delete_qtemplate]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "qtemplate_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Get all quotation [GET /user/quotation]


+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "quotations": [
                    {
                        "id": 1,
                        "quotations_number": "4545",
                        "date": "2015-11-11",
                        "customer": "customer name",
                        "person": "person name",
                        "total": "12",
                        "status": "1"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Post quotation [POST /user/post_quotation]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "customer_id": "1",
                "date": "2015-11-11",
                "qtemplate_id": "1",
                "pricelist_id": "12",
                "payment_term": "term",
                "sales_person": "1",
                "sales_team_id": "1",
                "grand_total": "12.5"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Edit quotation [POST /user/edit_quotation]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "quotation_id": "1",
                "customer_id": "1",
                "date": "2015-11-11",
                "qtemplate_id": "1",
                "pricelist_id": "12",
                "payment_term": "term",
                "sales_person": "1",
                "sales_team_id": "1",
                "grand_total": "12.5"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Delete quotation [POST /user/delete_quotation]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "quotation_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Get all sales order [GET /user/sales_order]


+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "salesorder": [
                    {
                        "id": 1,
                        "quotations_number": "product name",
                        "date": "2015-11-11",
                        "customer": "customer name",
                        "person": "sales person name",
                        "total": "12.53",
                        "status": "1"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Get all salesteam [GET /user/salesteam]


+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "salesteam": [
                    {
                        "id": 1,
                        "salesteam": "Name of team",
                        "target": "111",
                        "invoice_forecast": "1125",
                        "actual_invoice": "205"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Post salesteam [POST /user/post_salesteam]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "salesteam": "Title",
                "invoice_target": "8",
                "invoice_forecast": "1",
                "team_leader": "12",
                "team_members": "1,2,5"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Edit salesteam [POST /user/edit_salesteam]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "salesteam_id": "1",
                "salesteam": "Title",
                "invoice_target": "8",
                "invoice_forecast": "1",
                "team_leader": "12",
                "team_members": "1,2,5"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Delete salesteam [POST /user/delete_salesteam]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "salesteam_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Get all staff [GET /user/staff]


+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "staffs": [
                    {
                        "id": 1,
                        "full_name": "product name",
                        "email": "email@email.com",
                        "created_at": "2015-11-11"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Post staff [POST /user/post_staff]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "first_name": "first name",
                "last_name": "last name",
                "email": "email@email.com",
                "password": "1password"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Edit staff [POST /user/edit_staff]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "staff_id": "1",
                "first_name": "first name",
                "last_name": "last name",
                "password": "1password"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Delete staff [POST /user/delete_staff]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "staff_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }