@isTest
global class MockHttpResponseGenerator implements HttpCalloutMock{
	// Implement this interface method
    global HTTPResponse respond(HTTPRequest req) {
        // Optionally, only send a mock response for a specific endpoint
        // and method.
        System.assertEquals('https://64bjp0q5wg.execute-api.us-east-2.amazonaws.com/Implement/', req.getEndpoint());
        System.assertEquals('GET', req.getMethod());
        
        // Create a fake response
        HttpResponse res = new HttpResponse();
        res.setHeader('Content-Type', 'application/json');
        string g = '{"statusCode": 200,"body": {"Inventory": [  {"name": "CL1010_Inv","ProductID": "CL1010","Quan": 8589,"BlockedQuan": 40},{"name": "MC1020_Inv","ProductID": "MC1020","Quan": 7605,"BlockedQuan": 75},{"name": "DLL1030_Inv","ProductID": "DLL1030","Quan": 9784,"BlockedQuan": 14}]}}';
        res.setBody(g);
        res.setStatusCode(200);
        return res;
    }
}