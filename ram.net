using System.IO;
using Microsoft.AspNetCore.Mvc;
using Microsoft.Azure.Functions.Worker;
using Microsoft.Extensions.Logging;
using System.Net;

public static class dheerajfun
{
    [Function("dheerajfun")]
    public static HttpResponseData Run(
        [HttpTrigger(AuthorizationLevel.Function, "get", "post")] HttpRequestData req,
        FunctionContext context)
    {
        var logger = context.GetLogger("HttpTrigger1");
        logger.LogInformation("C# HTTP trigger function processed a request.");

        string name = req.Query["name"];

        if (string.IsNullOrEmpty(name))
        {
            return req.CreateResponse(HttpStatusCode.BadRequest, "Please provide a name.");
        }

        var response = req.CreateResponse(HttpStatusCode.OK);
        response.WriteString($"Hello, {name}!");

        return response;
    }
}
