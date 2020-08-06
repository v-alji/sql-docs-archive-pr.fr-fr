---
title: Rôle de SOAP dans Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], SOAP
- SOAP [Reporting Services], role in Reporting Services
- Report Server Web service, SOAP
- XML Web service [Reporting Services], SOAP
ms.assetid: f229c3ef-f2ca-448f-98f1-b8df350b9992
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 05445eb1c95c5761595944867b6d0c20a6f1a412
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700812"
---
# <a name="the-role-of-soap-in-reporting-services"></a><span data-ttu-id="23c78-102">Rôle de SOAP dans Reporting Services</span><span class="sxs-lookup"><span data-stu-id="23c78-102">The Role of SOAP in Reporting Services</span></span>
  <span data-ttu-id="23c78-103">Le service Web Report Server utilise la messagerie SOAP (Simple Object Access Protocol) pour envoyer des commandes textuelles sur un réseau.</span><span class="sxs-lookup"><span data-stu-id="23c78-103">The Report Server Web service uses Simple Object Access Protocol (SOAP) messaging to send text-based commands over a network.</span></span> <span data-ttu-id="23c78-104">Ces commandes prennent la forme de texte XML envoyé sur le Web à l'aide du protocole HTTP.</span><span class="sxs-lookup"><span data-stu-id="23c78-104">These commands take the form of XML text that is sent over the World Wide Web using HTTP.</span></span> <span data-ttu-id="23c78-105">En utilisant SOAP en tant que protocole de communication, le service Web Report Server permet aux applications et aux composants d'échanger des données avec le serveur de rapports à l'aide d'une infrastructure ouverte et largement reconnue.</span><span class="sxs-lookup"><span data-stu-id="23c78-105">By using SOAP as its communication protocol, the Report Server Web service allows applications and components to exchange data with the report server using an open and widely accepted infrastructure.</span></span> <span data-ttu-id="23c78-106">La norme SOAP est définie sur le site www.w3.org/TR/SOAP.</span><span class="sxs-lookup"><span data-stu-id="23c78-106">The SOAP standard is defined at www.w3.org/TR/SOAP.</span></span>  
  
 <span data-ttu-id="23c78-107">Toute application cliente peut jouer le rôle de client SOAP dans la mesure où elle prend en charge le protocole SOAP et où elle peut envoyer des demandes SOAP.</span><span class="sxs-lookup"><span data-stu-id="23c78-107">Any client application can act as a SOAP client as long as it is SOAP-aware and can send SOAP requests.</span></span> <span data-ttu-id="23c78-108">Le Gestionnaire de rapports est l'un de ces clients SOAP.</span><span class="sxs-lookup"><span data-stu-id="23c78-108">Report Manager is one such SOAP client.</span></span> <span data-ttu-id="23c78-109">Il fournit une interface à la base de données du serveur de rapports dans laquelle tous les rapports et leur contenu associé sont stockés.</span><span class="sxs-lookup"><span data-stu-id="23c78-109">It provides an interface to the report server database in which all reports and report-related content is stored.</span></span> <span data-ttu-id="23c78-110">Les utilisateurs finals peuvent utiliser l'application pour parcourir et gérer des rapports et des dossiers dans l'espace de noms du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="23c78-110">End users can use the application to browse through and manage reports and folders in the report server namespace.</span></span> <span data-ttu-id="23c78-111">Le Gestionnaire de rapports repose sur l'infrastructure du service Web Report Server.</span><span class="sxs-lookup"><span data-stu-id="23c78-111">Report Manager is built on the Report Server Web service infrastructure.</span></span>  
  
 <span data-ttu-id="23c78-112">Un serveur de rapports joue le rôle de serveur SOAP, un service prenant en charge le protocole SOAP qui peut accepter des demandes en provenance de clients SOAP et créer des réponses appropriées.</span><span class="sxs-lookup"><span data-stu-id="23c78-112">A report server acts as a SOAP server, a SOAP-aware service that can accept requests from SOAP clients and create appropriate responses.</span></span> <span data-ttu-id="23c78-113">Le serveur gère les demandes et renvoie des réponses encodées au client.</span><span class="sxs-lookup"><span data-stu-id="23c78-113">The server handles the requests and sends encoded responses back to the client.</span></span>  
  
 <span data-ttu-id="23c78-114">Les messages SOAP dans [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] prennent de nombreuses formes différentes, selon le type de demande faite par le client.</span><span class="sxs-lookup"><span data-stu-id="23c78-114">SOAP messages in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] take many different forms, depending on the type of request made by the client.</span></span> <span data-ttu-id="23c78-115">L'exemple suivant représente une requête simple d'un client SOAP consistant à supprimer un élément de la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="23c78-115">The following example represents a simple SOAP client request to remove an item from the report server database.</span></span>  
  
```  
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <soap:Body>  
        <DeleteItem xmlns="https://www.microsoft.com/sql/ReportingServer">  
            <item>/Samples/Report1</item>  
        </DeleteItem>  
    </soap:Body>  
</soap:Envelope>  
```  
  
 <span data-ttu-id="23c78-116">Le protocole SOAP requiert que les messages soient placés dans un élément `Envelope`, avec le plus gros du message à l'intérieur d'un élément `Body`.</span><span class="sxs-lookup"><span data-stu-id="23c78-116">The SOAP itself requires that messages be put into an `Envelope` element, with the bulk of the message inside a `Body` element.</span></span> <span data-ttu-id="23c78-117">Dans cet exemple, le corps contient un appel de la méthode <xref:ReportService2010.ReportingService2010.DeleteItem%2A>, qui prend un paramètre de chaîne représentant le chemin d'accès de l'élément à supprimer.</span><span class="sxs-lookup"><span data-stu-id="23c78-117">In this example, the body contains a call to the <xref:ReportService2010.ReportingService2010.DeleteItem%2A> method, which takes a string parameter representing the path of the item to delete.</span></span> <span data-ttu-id="23c78-118">Vous pouvez créer une [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classe de proxy client qui encapsule toutes les opérations SOAP dans des méthodes.</span><span class="sxs-lookup"><span data-stu-id="23c78-118">You can create a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] client proxy class that encapsulates all SOAP operations into methods.</span></span> <span data-ttu-id="23c78-119">La [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] méthode suivante représente l’exemple SOAP donné précédemment.</span><span class="sxs-lookup"><span data-stu-id="23c78-119">The following [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] method represents the SOAP example given earlier.</span></span>  
  
```  
public void DeleteItem(string item);  
```  
  
 <span data-ttu-id="23c78-120">La réponse du serveur peut ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="23c78-120">The response from the server might look like the following:</span></span>  
  
```  
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <soap:Body>  
        <DeleteItemResponse xmlns="https://www.microsoft.com/sql/ReportingServer" />  
    </soap:Body>  
</soap:Envelope>  
```  
  
 <span data-ttu-id="23c78-121">La méthode <xref:ReportService2010.ReportingService2010.DeleteItem%2A> n'a aucune valeur de retour, donc une réponse vide est retournée.</span><span class="sxs-lookup"><span data-stu-id="23c78-121">The <xref:ReportService2010.ReportingService2010.DeleteItem%2A> method has no return value, so an empty response is returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23c78-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="23c78-122">See Also</span></span>  
 <span data-ttu-id="23c78-123">[Accès à l’API SOAP](accessing-the-soap-api.md) </span><span class="sxs-lookup"><span data-stu-id="23c78-123">[Accessing the SOAP API](accessing-the-soap-api.md) </span></span>  
 <span data-ttu-id="23c78-124">[Gestionnaire de rapports &#40;SSRS en mode natif&#41;](../report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="23c78-124">[Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="23c78-125">[Reporting Services le serveur de rapports](../reporting-services-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="23c78-125">[Reporting Services Report Server](../reporting-services-report-server.md) </span></span>  
 [<span data-ttu-id="23c78-126">Service Web des serveurs de rapports</span><span class="sxs-lookup"><span data-stu-id="23c78-126">Report Server Web Service</span></span>](report-server-web-service.md)  
  
  
