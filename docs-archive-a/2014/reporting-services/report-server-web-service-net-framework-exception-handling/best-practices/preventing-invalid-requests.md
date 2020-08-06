---
title: Éviter les requêtes non valides | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- invalid requests [Reporting Services]
- exceptions [Reporting Services], invalid requests
- valid requests [Reporting Services]
ms.assetid: 4a4a2d97-4c10-43a9-8298-ef5a820ea549
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 12343955c46fb98fea75048a38749b1db993fa11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613297"
---
# <a name="preventing-invalid-requests"></a><span data-ttu-id="5e359-102">Éviter les demandes non valides</span><span class="sxs-lookup"><span data-stu-id="5e359-102">Preventing Invalid Requests</span></span>
  <span data-ttu-id="5e359-103">Vous pouvez éviter que certains types d'exceptions soient levés en analysant le flux de votre application et en veillant à ce que les demandes qui sont envoyées au serveur de rapports soient valides.</span><span class="sxs-lookup"><span data-stu-id="5e359-103">You can prevent some types of exceptions from being thrown by analyzing your application flow and ensuring that the requests being sent to the report server are valid.</span></span> <span data-ttu-id="5e359-104">Par exemple, dans les applications qui permettent aux utilisateurs d'ajouter ou de mettre à jour le nom d'un rapport, d'une source de données ou d'autres éléments de serveur de rapports, vous devez valider le texte entré par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5e359-104">For example, in applications that enable users to add or update the name of a report, data source, or other report server item, you should validate the text that a user might enter.</span></span> <span data-ttu-id="5e359-105">Vous devez toujours vérifier que la demande ne contient pas de caractères réservés avant de l'envoyer à un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="5e359-105">You should always check for reserved characters before sending the request to a report server.</span></span> <span data-ttu-id="5e359-106">Utilisez des instructions **if** conditionnelles ou d’autres constructions logiques dans votre code pour avertir l’utilisateur que les conditions nécessaires à l’envoi de demandes au serveur de rapports n’ont pas été réunies.</span><span class="sxs-lookup"><span data-stu-id="5e359-106">Use conditional **if** statements or other logical constructs in your code to alert the user that they have not met the conditions necessary to send requests to the report server.</span></span>  
  
 <span data-ttu-id="5e359-107">Dans l'exemple C# simplifié suivant, un message d'erreur convivial s'affiche lorsque les utilisateurs essaient de créer un rapport dont le nom contient une barre oblique (/).</span><span class="sxs-lookup"><span data-stu-id="5e359-107">In the following, simplified C# example, users are presented with a friendly error message when they attempt to create a report with a name that contains a forward slash (/) character.</span></span>  
  
```  
// C#  
private void PublishReport()  
{  
   int index;  
   string reservedChar;  
   string message;  
  
   // Check the text value of the name text box for "/",  
   // a reserved character  
   index = nameTextBox.Text.IndexOf(@"/");  
  
   if ( index != -1) // The text contains the character  
   {  
      reservedChar = nameTextBox.Text.Substring(index, 1);  
      // Build a user-friendly error message  
      message = "The name of the report cannot contain the reserved character " +  
         "\"" + reservedChar + "\". " +  
         "Please enter a valid name for the report. " +  
         "For more information about reserved characters, " +  
         "see the help documentation";  
  
      MessageBox.Show(message, "Invalid Input Error");  
   }  
   else // Publish the report  
   {  
      Byte[] definition = null;  
      Warning[] warnings = {};  
      string name = nameTextBox.Text;  
  
      FileStream stream = File.OpenRead("MyReport.rdl");  
      definition = new Byte[stream.Length];  
      stream.Read(definition, 0, (int) stream.Length);  
      stream.Close();  
      // Create report with user-defined name  
      rs.CreateCatalogItem("Report", name, "/Samples", false, definition, null, out warnings);  
      MessageBox.Show("Report: {0} created successfully", name);  
   }  
}  
```  
  
 <span data-ttu-id="5e359-108">Pour plus d’informations sur les types d’erreurs qui peuvent être évitées avant l’envoi de demandes au serveur de rapports, consultez [Table d’erreurs SoapException](../soapexception-class/soapexception-errors-table.md).</span><span class="sxs-lookup"><span data-stu-id="5e359-108">For more information about the types of errors that can be prevented before requests are sent to the report server, see [SoapException Errors Table](../soapexception-class/soapexception-errors-table.md).</span></span> <span data-ttu-id="5e359-109">Pour plus d’informations sur la manière d’améliorer l’exemple précédent à l’aide de blocs try/catch, consultez [Utilisation des blocs Try/Catch](using-try-and-catch-blocks.md).</span><span class="sxs-lookup"><span data-stu-id="5e359-109">For more information about further enhancing the previous example using try/catch blocks, see [Using Try and Catch Blocks](using-try-and-catch-blocks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e359-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5e359-110">See Also</span></span>  
 <span data-ttu-id="5e359-111">[Présentation de la gestion des exceptions dans Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="5e359-111">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="5e359-112">Classe SoapException Reporting Services</span><span class="sxs-lookup"><span data-stu-id="5e359-112">Reporting Services SoapException Class</span></span>](../soapexception-class/reporting-services-soapexception-class.md)  
  
  
