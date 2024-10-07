My Salesforce Link
https://www.salesforce.com/trailblazer/h2s28hciybnegoelnn

 Code Snippet : (Apex class)

class ConsumerRecord {
    public static void sendEmailNotification (List<consumer__c> con){
        for(consumer__c c:con)
        {
            Messaging.SingleEmailMessage email = new Messaging.SingleEmailMessage();
                email.setToAddresses( new List<String>{c.email__c});
                email.setSubject('Welcome to our company');
                email.setPlainTextBody('Dear '  + ' '+ ',\n\nWelcome to MY RICE!'+'You have been seen as a valuable customer to us. PLease continue your journey with us, while we try to provide you with good quality resources.'+'\n'+
                                           "We are proud to associate with valuable customers like you and we look forward to collaborating with you by providing more and more exciting discounts or even product offers too.' + '\n'
                                           +'So why taking a step back, take a leap of faith and shop with us more, while we provide with the valuable products and offers'+'\n'+'\n'+'\n'+
                                           'Thankyou for buying '+ '' +'Here are some of the products that are brought by the customers who similarly bought products like this'+'\n\n');
                Messaging.sendEmail(new List<Messaging.SingleEmailMessage>{email});

        }
    }
}

(Apex trigger)
trigger consumerTrigger on consumer__c (After insert) {
    if(trigger.isAfter && trigger.isInsert) {
        ConsumerRecord.sendEmailNotification(trigger.new);
    }
}
 Rice-Mill
 Project Title : A CRM APPLICATION FOR WHOLESALE RICE MILL
 Created Objects named supplier, rice mill, rice details etc
 Created Tabs for the Objects, they are “ rice mill, consumer , rice details”.
 
 To create a lightning app page:
Go to setup page >> search “app manager” in quick find >> select “app manager” >> click on New lightning App.

Types of Fields:
    - Standard Fields 
    - Custom Fields 
    
Page Layout in Salesforce allows us to customize the design and organize detail and edit pages of records in Salesforce.

Profiles
A profile is a group/collection of settings and permissions that define what a user can do in salesforce. 
Types of profiles in salesforce 
   - Standard profiles
   - Custom Profiles
