---
title: 'Leçon 2 : ajout d’une référence Web | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a2c2b8b8-6b13-45ca-ab3b-1582447b6807
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 02ca614cb042211ac468246c3003efaa5f2e8fb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702216"
---
# <a name="lesson-2-adding-a-web-reference"></a><span data-ttu-id="0e7ad-102">Leçon 2 : Ajout d’une référence web</span><span class="sxs-lookup"><span data-stu-id="0e7ad-102">Lesson 2: Adding a Web Reference</span></span>
  <span data-ttu-id="0e7ad-103">La découverte de service Web est le processus suivant lequel un client recherche un service Web et obtient sa description.</span><span class="sxs-lookup"><span data-stu-id="0e7ad-103">Web service discovery is the process by which a client locates a Web service and obtains its service description.</span></span> <span data-ttu-id="0e7ad-104">Dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], le processus de la découverte de service Web implique l'interrogation d'un site Web suivant un algorithme prédéterminé.</span><span class="sxs-lookup"><span data-stu-id="0e7ad-104">The process of Web service discovery in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] involves interrogating a Web site following a predetermined algorithm.</span></span> <span data-ttu-id="0e7ad-105">L'objectif de ce processus est de rechercher la description du service, qui correspond à un document XML utilisant le langage WSDL (Web Services Description Language).</span><span class="sxs-lookup"><span data-stu-id="0e7ad-105">The goal of the process is to locate the service description, which is an XML document that uses the Web Services Description Language (WSDL).</span></span>  
  
 <span data-ttu-id="0e7ad-106">La description du service décrit les services disponibles et la manière d'interagir avec ces derniers.</span><span class="sxs-lookup"><span data-stu-id="0e7ad-106">The service description describes what services are available and how to interact with those services.</span></span> <span data-ttu-id="0e7ad-107">Sans une description de service, il est impossible d'interagir par programme avec un service Web.</span><span class="sxs-lookup"><span data-stu-id="0e7ad-107">Without a service description, it is impossible to programmatically interact with a Web service.</span></span>  
  
 <span data-ttu-id="0e7ad-108">Votre application doit pouvoir communiquer avec le service Web et le rechercher lors de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="0e7ad-108">Your application must have a means to communicate with the Web service and to locate it at run time.</span></span> <span data-ttu-id="0e7ad-109">L'ajout d'une référence Web à votre projet pour le service Web permet cela en générant une classe proxy qui joue le rôle d'interface avec le service Web et qui en fournit une représentation locale.</span><span class="sxs-lookup"><span data-stu-id="0e7ad-109">Adding a Web reference to your project for the Web service does this by generating a proxy class that interfaces with the Web service and provides a local representation of the Web service.</span></span> <span data-ttu-id="0e7ad-110">Pour plus d'informations, consultez « Procédure : générer un XML d'un proxy de service Web » dans la documentation [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e7ad-110">For more information, see "How to: Generate an XML Web Service Proxy" in your [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] documentation.</span></span>  
  
### <a name="to-add-a-web-reference"></a><span data-ttu-id="0e7ad-111">Pour ajouter une référence Web</span><span class="sxs-lookup"><span data-stu-id="0e7ad-111">To add a Web reference</span></span>  
  
1.  <span data-ttu-id="0e7ad-112">Dans le menu **projet** , cliquez sur **Ajouter une référence de service**.</span><span class="sxs-lookup"><span data-stu-id="0e7ad-112">On the **Project** menu, click **Add Service Reference**.</span></span>  
  
2.  <span data-ttu-id="0e7ad-113">Dans la boîte de dialogue **Ajouter une référence de service** , cliquez sur **avancé**.</span><span class="sxs-lookup"><span data-stu-id="0e7ad-113">In the **Add Service Reference** dialog box, click **Advanced**.</span></span>  
  
3.  <span data-ttu-id="0e7ad-114">Dans la boîte de dialogue **paramètres de référence de service** , cliquez sur Ajouter une **référence Web**.</span><span class="sxs-lookup"><span data-stu-id="0e7ad-114">In the **Service Reference Settings** dialog box, click **Add Web Reference**.</span></span>  
  
4.  <span data-ttu-id="0e7ad-115">Dans la zone **URL** de la boîte de dialogue **Ajouter une référence Web** , tapez l’URL permettant d’obtenir la description de service du service Web Report Server, telle que http://localhost/reportserver/reportservice2010.asmx .</span><span class="sxs-lookup"><span data-stu-id="0e7ad-115">In the **URL** box of the **Add Web Reference** dialog box, type the URL to obtain the service description of the Report Server Web service, such as http://localhost/reportserver/reportservice2010.asmx.</span></span> <span data-ttu-id="0e7ad-116">Cliquez ensuite sur le bouton **OK** pour récupérer des informations sur le service Web.</span><span class="sxs-lookup"><span data-stu-id="0e7ad-116">Then click the **Go** button to retrieve information about the Web service.</span></span>  
  
     <span data-ttu-id="0e7ad-117">\- ou -</span><span class="sxs-lookup"><span data-stu-id="0e7ad-117">\- or -</span></span>  
  
     <span data-ttu-id="0e7ad-118">Si le service Web Report Server existe sur l’ordinateur local, cliquez sur le lien **services Web sur l’ordinateur local** dans le volet navigateur.</span><span class="sxs-lookup"><span data-stu-id="0e7ad-118">If the Report Server Web service exists on the local machine, click the **Web services on the local machine** link in the browser pane.</span></span> <span data-ttu-id="0e7ad-119">Cliquez ensuite sur le lien du service Web ReportService2010 dans la liste fournie.</span><span class="sxs-lookup"><span data-stu-id="0e7ad-119">Then click the link for the ReportService2010 Web service from the list provided.</span></span>  
  
5.  <span data-ttu-id="0e7ad-120">Dans la zone nom de la **référence Web** , renommez la référence Web en ReportService2010, qui est l’espace de noms que vous allez utiliser pour cette référence Web.</span><span class="sxs-lookup"><span data-stu-id="0e7ad-120">In the **Web reference name** box, rename the Web reference to ReportService2010, which is the namespace you will use for this Web reference.</span></span>  
  
6.  <span data-ttu-id="0e7ad-121">Cliquez sur **Ajouter une référence** pour ajouter une référence Web pour le service Web cible.</span><span class="sxs-lookup"><span data-stu-id="0e7ad-121">Click **Add Reference** to add a Web reference for the target Web service.</span></span>  
  
     [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] <span data-ttu-id="0e7ad-122">télécharge la description du service et génère une classe proxy pour jouer le rôle d'interface entre votre application et le service Web Report Server.</span><span class="sxs-lookup"><span data-stu-id="0e7ad-122">downloads the service description and generates a proxy class to interface between your application and the Report Server Web service.</span></span> <span data-ttu-id="0e7ad-123">Vous devrez également ajouter une référence à l'espace de noms <xref:System.Web.Services> pour que votre référence Web fonctionne.</span><span class="sxs-lookup"><span data-stu-id="0e7ad-123">You will also need to add a reference to the <xref:System.Web.Services> namespace for your Web reference to work.</span></span>  
  
7.  <span data-ttu-id="0e7ad-124">Dans le menu Projet, cliquez sur **Ajouter une référence**.</span><span class="sxs-lookup"><span data-stu-id="0e7ad-124">On the Project menu, click **Add Reference**.</span></span>  
  
8.  <span data-ttu-id="0e7ad-125">Dans la boîte de dialogue **Ajouter une référence** , dans l'onglet **.NET** , sélectionnez **System.Web.Services**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e7ad-125">In the **Add Reference** dialog box, in the **.NET** tab, select **System.Web.Services**, then click **OK**.</span></span>  
  
 <span data-ttu-id="0e7ad-126">Pour plus d’informations, consultez [Accès à l’API SOAP](../reporting-services/report-server-web-service/accessing-the-soap-api.md).</span><span class="sxs-lookup"><span data-stu-id="0e7ad-126">For more information, see [Accessing the SOAP API](../reporting-services/report-server-web-service/accessing-the-soap-api.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e7ad-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0e7ad-127">See Also</span></span>  
 <span data-ttu-id="0e7ad-128">[Service web Report Server](../reporting-services/report-server-web-service/report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="0e7ad-128">[Report Server Web Service](../reporting-services/report-server-web-service/report-server-web-service.md) </span></span>  
 <span data-ttu-id="0e7ad-129">[Leçon 3 : accès au service Web](../../2014/tutorials/lesson-3-accessing-the-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="0e7ad-129">[Lesson 3: Accessing the Web Service](../../2014/tutorials/lesson-3-accessing-the-web-service.md) </span></span>  
 [<span data-ttu-id="0e7ad-130">Accès au service Web Report Server à l’aide de Visual Basic ou du didacticiel Visual C&#35; &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0e7ad-130">Accessing the Report Server Web Service Using Visual Basic or Visual C&#35; &#40;SSRS Tutorial&#41;</span></span>](../../2014/tutorials/access-report-server-web-service-vb-vcsharp-ssrs-tutorial.md)  
  
  
