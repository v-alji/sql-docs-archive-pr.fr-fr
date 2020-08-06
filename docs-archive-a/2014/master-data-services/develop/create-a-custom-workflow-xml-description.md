---
title: Description du code XML d’un flux de travail personnalisé (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: e267e5f4-38bb-466d-82e8-871eabeec07e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 77906426ddb901ec422367bf30aabef2e532ad06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615179"
---
# <a name="custom-workflow-xml-description-master-data-services"></a><span data-ttu-id="f3b0f-102">Description personnalisée XML de flux de travail (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f3b0f-102">Custom Workflow XML Description (Master Data Services)</span></span>
  <span data-ttu-id="f3b0f-103">Dans [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] , la méthode [Microsoft. MasterDataServices. WorkflowTypeExtender. IWorkflowTypeExtender. StartWorkflow \*](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)) est appelée par SQL Server Service d’intégration de flux de travail MDS au démarrage d’un flux de travail.</span><span class="sxs-lookup"><span data-stu-id="f3b0f-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)], the [Microsoft.MasterDataServices.WorkflowTypeExtender.IWorkflowTypeExtender.StartWorkflow\*](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)) method is called by SQL Server MDS Workflow Integration Service when a workflow starts.</span></span> <span data-ttu-id="f3b0f-104">Cette méthode reçoit les métadonnées et les données relatives à l'élément qui a déclenché la règle d'entreprise de flux de travail sous la forme d'un bloc XML.</span><span class="sxs-lookup"><span data-stu-id="f3b0f-104">This method receives metadata and data about the item that triggered the workflow business rule as a block of XML.</span></span> <span data-ttu-id="f3b0f-105">Pour découvrir un exemple de code qui implémente un gestionnaire de flux de travail, consultez [Exemple de flux de travail personnalisé &#40;Master Data Services&#41;](create-a-custom-workflow-example.md).</span><span class="sxs-lookup"><span data-stu-id="f3b0f-105">For example code that implements a workflow handler, see [Custom Workflow Example &#40;Master Data Services&#41;](create-a-custom-workflow-example.md).</span></span>  
  
 <span data-ttu-id="f3b0f-106">L'exemple suivant montre à quoi ressemble le code XML envoyé au gestionnaire de flux de travail :</span><span class="sxs-lookup"><span data-stu-id="f3b0f-106">The following example shows what the XML that is sent to the workflow handler might look like:</span></span>  
  
```scr  
<ExternalAction>  
  <Type>TEST</Type>  
  <SendData>1</SendData>  
  <Server_URL>This is my test!</Server_URL>  
  <Action_ID>Test Workflow</Action_ID>  
  <Model_ID>5</Model_ID>  
  <Model_Name>Customer</Model_Name>  
  <Entity_ID>34</Entity_ID>  
  <Entity_Name>Customer</Entity_Name>  
  <Version_ID>8</Version_ID>  
  <MemberType_ID>1</MemberType_ID>  
  <Member_ID>12</Member_ID>  
  <MemberData>  
    <ID>12</ID>  
    <Version_ID>8</Version_ID>  
    <ValidationStatus_ID>3</ValidationStatus_ID>  
    <ChangeTrackingMask>0</ChangeTrackingMask>  
    <EnterDTM>2011-02-25T20:16:36.650</EnterDTM>  
    <EnterUserID>2</EnterUserID>  
    <EnterUserName>MyUserName</EnterUserName>  
    <EnterUserMuid>EEF91D48-B673-4D83-B95F-5A363C11DE91</EnterUserMuid>  
    <EnterVersionId>8</EnterVersionId>  
    <EnterVersionName>VERSION_1</EnterVersionName>  
    <EnterVersionMuid>52B788C2-2750-4651-9DB0-2CB05A88AA5A</EnterVersionMuid>  
    <LastChgDTM>2011-02-25T20:16:36.650</LastChgDTM>  
    <LastChgUserID>2</LastChgUserID>  
    <LastChgUserName>MyUserName</LastChgUserName>  
    <LastChgUserMuid>EEF91D48-B673-4D83-B95F-5A363C11DE91</LastChgUserMuid>  
    <LastChgVersionId>8</LastChgVersionId>  
    <LastChgVersionName>VERSION_1</LastChgVersionName>  
    <LastChgVersionMuid>52B788C2-2750-4651-9DB0-2CB05A88AA5A</LastChgVersionMuid>  
    <Name>Test Customer</Name>  
    <Code>TC</Code>  
  </MemberData>  
</ExternalAction>  
```  
  
 <span data-ttu-id="f3b0f-107">Le tableau suivant décrit quelques-unes des balises contenues dans ce code XML :</span><span class="sxs-lookup"><span data-stu-id="f3b0f-107">The following table describes some of the tags contained in this XML:</span></span>  
  
|<span data-ttu-id="f3b0f-108">Tag</span><span class="sxs-lookup"><span data-stu-id="f3b0f-108">Tag</span></span>|<span data-ttu-id="f3b0f-109">Description</span><span class="sxs-lookup"><span data-stu-id="f3b0f-109">Description</span></span>|  
|---------|-----------------|  
|\<Type>|<span data-ttu-id="f3b0f-110">Texte que vous avez entré dans la zone de texte **Type de flux de travail** dans [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] pour identifier quels assemblys personnalisés de flux de travail doivent être chargés.</span><span class="sxs-lookup"><span data-stu-id="f3b0f-110">The text you entered in the **Workflow type** text box in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] to identify which custom workflow assembly to load.</span></span>|  
|\<SendData>|<span data-ttu-id="f3b0f-111">Valeur booléenne contrôlée par la case à cocher **Inclure les données de membre dans le message** dans [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3b0f-111">A Boolean value controlled by the **Include member data in the message** checkbox in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span> <span data-ttu-id="f3b0f-112">La valeur 1 signifie que la \<MemberData> section est envoyée ; sinon, la \<MemberData> section n’est pas envoyée.</span><span class="sxs-lookup"><span data-stu-id="f3b0f-112">A value of 1 means that the \<MemberData> section is sent; otherwise the \<MemberData> section is not sent.</span></span>|  
|<span data-ttu-id="f3b0f-113"><Server_URL></span><span class="sxs-lookup"><span data-stu-id="f3b0f-113"><Server_URL></span></span>|<span data-ttu-id="f3b0f-114">Texte que vous avez entré dans la zone de texte **Site du flux de travail** dans [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3b0f-114">The text you entered in the **Workflow site** text box in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span>|  
|<span data-ttu-id="f3b0f-115"><Action_ID></span><span class="sxs-lookup"><span data-stu-id="f3b0f-115"><Action_ID></span></span>|<span data-ttu-id="f3b0f-116">Texte que vous avez entré dans la zone de texte **Nom du flux de travail** dans [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3b0f-116">The text you entered in the **Workflow name** text box in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span>|  
|\<MemberData>|<span data-ttu-id="f3b0f-117">Contient les données du membre qui a déclenché l'action de flux de travail.</span><span class="sxs-lookup"><span data-stu-id="f3b0f-117">Contains the data of the member that triggered the workflow action.</span></span> <span data-ttu-id="f3b0f-118">Cela est inclus uniquement si la valeur de \<SendData> est 1.</span><span class="sxs-lookup"><span data-stu-id="f3b0f-118">This is included only if the value of \<SendData> is 1.</span></span>|  
|\<Enter*xxx*>|<span data-ttu-id="f3b0f-119">Cet ensemble de balises contient des métadonnées sur la création du membre, comme sa date de création et la personne qui l'a créé.</span><span class="sxs-lookup"><span data-stu-id="f3b0f-119">This set of tags contains metadata about the creation of the member, such as when it was created and who created it.</span></span>|  
|\<LastChg*xxx*>|<span data-ttu-id="f3b0f-120">Cet ensemble de balises contient des métadonnées sur la dernière modification apportée au membre, comme la date de la modification et la personne qui l'a effectuée.</span><span class="sxs-lookup"><span data-stu-id="f3b0f-120">This set of tags contains metadata about the last change made to the member, such as when the change was made and who made it.</span></span>|  
|\<Name>|<span data-ttu-id="f3b0f-121">Premier attribut du membre qui a été modifié.</span><span class="sxs-lookup"><span data-stu-id="f3b0f-121">The first attribute of the member that was changed.</span></span> <span data-ttu-id="f3b0f-122">Cet exemple de membre contient uniquement des attributs Name et Code.</span><span class="sxs-lookup"><span data-stu-id="f3b0f-122">This example member contains only Name and Code attributes.</span></span>|  
|\<Code>|<span data-ttu-id="f3b0f-123">Attribut suivant du membre qui a été modifié.</span><span class="sxs-lookup"><span data-stu-id="f3b0f-123">The next attribute of the member that was changed.</span></span> <span data-ttu-id="f3b0f-124">Si cet exemple de membre contenait plus d'attributs, ils suivraient celui-ci.</span><span class="sxs-lookup"><span data-stu-id="f3b0f-124">If this example member contained more attributes, they would follow this one.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f3b0f-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f3b0f-125">See Also</span></span>  
 <span data-ttu-id="f3b0f-126">[Créer un &#40;de flux de travail personnalisé Master Data Services&#41;](create-a-custom-workflow-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="f3b0f-126">[Create a Custom Workflow &#40;Master Data Services&#41;](create-a-custom-workflow-master-data-services.md) </span></span>  
 [<span data-ttu-id="f3b0f-127">Exemple de flux de travail personnalisé &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f3b0f-127">Custom Workflow Example &#40;Master Data Services&#41;</span></span>](create-a-custom-workflow-example.md)  
  
  
