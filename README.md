# Akinator.Api.UWP
Ported from https://github.com/janniksam/Akinator.Api.Net with some little changes.

[![NuGet version](https://badge.fury.io/nu/Akinator.UWP.svg)](https://badge.fury.io/nu/Akinator.UWP)

### Orignally created by [janniksam](https://github.com/janniksam)

## Supported Launguges
* English (*Person*, *Object*, *Animal*)
* France (*Person*, *Object*, *Animal*)
* Arabic (*Person*)
* Italian (*Person*)
* Spanish (*Person*)
* Russian (*Person*)
* German (*Person*, *Animal*)
* Russian (*Person*)

## Known issues

- Lack of supported servers and languages
- The GuessIsDue-method, which decides, when Akinator is ready to guess, needs to be improved significantly

## Basic usage

```cs
using (var client = new AkinatorClient(Language.German, ServerType.Person))
{
   // Start a new game
   var question = await client.StartNewGame(); 
   
   // Process question...
   // ...
   
   // Answer the previous question with "Yes" and get the next one
   var question = await client.Answer(AnswerOptions.Yes);
   
   // if Akinator is due to guess...
   if (client.GuessIsDue(question))
   {
      // Get Akinators guess..
      var guess = await client.GetGuess();
      // Verify the guess ...
   }
}
```
