


/apex/NewCasePopulate?id={!Account.Id}

public class NewCasePopulateController {

Public Account accDet{get;set;}
Public String accId;

public NewCasePopulateController (){
        accId= ApexPages.currentPage().getParameters().get('id');   
        accDet=[SELECT id,Tax_Name__c,Type,Account_type__c FROM Account where id=:accId]; 
        
              }
  public PageReference NextPage(){
      
    PageReference pr =new PageReference('/500/e?retURL=%2F500%2Fo&00NE0000003hErr='+accDet.Tax_Name__c+'&00NE0000003hEwb='+accDet.Account_type__c);
       system.debug('------'+accDet.Tax_Name__c+'---------');
        return pr;
    }
            

}

<apex:page extension="NewCasePopulate contoller">
</apex:apex>
