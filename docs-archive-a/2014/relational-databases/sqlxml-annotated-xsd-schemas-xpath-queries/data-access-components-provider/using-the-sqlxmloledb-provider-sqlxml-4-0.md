---
title: Utilisation du fournisseur SQLXMLOLEDB (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- sample applications [SQLXML]
- SQLXMLOLEDB Provider, samples
- ClientSideXML property
ms.assetid: fbcefac5-29c9-478b-b0e0-d510b593f446
author: rothja
ms.author: jroth
ms.openlocfilehash: 74e3c53eecd657d610c2fe90e108e0290e9b05b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610558"
---
# <a name="using-the-sqlxmloledb-provider-sqlxml-40"></a><span data-ttu-id="c56f2-102">Utilisation du fournisseur SQLXMLOLEDB (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="c56f2-102">Using the SQLXMLOLEDB Provider (SQLXML 4.0)</span></span>
  <span data-ttu-id="c56f2-103">Les rubriques de cette section présentent des exemples d'application ADO qui illustrent l'utilisation des propriétés spécifiques au fournisseur SQLXMLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="c56f2-103">The topics in this section provide ADO sample applications that illustrate the use of SQLXMLOLEDB Provider-specific properties.</span></span>  
  
## <a name="application-requirements-for-sqlxmloledb-40-provider"></a><span data-ttu-id="c56f2-104">Spécifications de l'application pour le fournisseur SQLXMLOLEDB 4.0</span><span class="sxs-lookup"><span data-stu-id="c56f2-104">Application Requirements for SQLXMLOLEDB 4.0 Provider</span></span>  
 <span data-ttu-id="c56f2-105">Pour créer des exemples fonctionnels qui utilisent SQLXMLOLEDB 4.0, vous devez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="c56f2-105">To create working samples that use SQLXMLOLEDB 4.0, you must do the following:</span></span>  
  
1.  <span data-ttu-id="c56f2-106">Créer une application Microsoft Visual Basic.exe et ajouter l'une des références suivantes :</span><span class="sxs-lookup"><span data-stu-id="c56f2-106">Create a Microsoft Visual Basic .exe application and add one of the following references:</span></span>  
  
    -   <span data-ttu-id="c56f2-107">Bibliothèque Microsoft ActiveX Data Objects 2,6</span><span class="sxs-lookup"><span data-stu-id="c56f2-107">Microsoft ActiveX Data Objects 2.6 Library</span></span>  
  
    -   <span data-ttu-id="c56f2-108">Bibliothèque Microsoft ActiveX Data Objects 2,7</span><span class="sxs-lookup"><span data-stu-id="c56f2-108">Microsoft ActiveX Data Objects 2.7 Library</span></span>  
  
    -   <span data-ttu-id="c56f2-109">Bibliothèque Microsoft ADO 2.8</span><span class="sxs-lookup"><span data-stu-id="c56f2-109">Microsoft ActiveX Data Objects 2.8 Library</span></span>  
  
2.  <span data-ttu-id="c56f2-110">Déployer et installer SQLXML 4.0 et [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="c56f2-110">Deploy and install SQLXML 4.0 and the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
     <span data-ttu-id="c56f2-111">Pour plus d’informations, consultez les [concepts de programmation de SQLXML 4,0](../../sqlxml/sqlxml-4-0-programming-concepts.md) et [installation de SQL Server Native Client](../../native-client/applications/installing-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="c56f2-111">For more information, see on [SQLXML 4.0 Programming Concepts](../../sqlxml/sqlxml-4-0-programming-concepts.md) and [Installing SQL Server Native Client](../../native-client/applications/installing-sql-server-native-client.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c56f2-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="c56f2-112">In This Section</span></span>  
 [<span data-ttu-id="c56f2-113">Exécution de requêtes SQL &#40;fournisseur SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="c56f2-113">Executing SQL Queries &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-sql-queries-sqlxmloledb-provider.md)  
 <span data-ttu-id="c56f2-114">Illustre l’utilisation des propriétés racine ClientSideXML et XML pour exécuter des requêtes SQL.</span><span class="sxs-lookup"><span data-stu-id="c56f2-114">Illustrates the use of the ClientSideXML and xml root properties to execute SQL queries.</span></span>  
  
 [<span data-ttu-id="c56f2-115">Exécution de modèles contenant des requêtes SQL &#40;fournisseur SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="c56f2-115">Executing Templates That Contain SQL Queries &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-templates-that-contain-sql-queries-sqlxmloledb-provider.md)  
 <span data-ttu-id="c56f2-116">Illustre l’utilisation de la propriété ClientSideXML.</span><span class="sxs-lookup"><span data-stu-id="c56f2-116">Illustrates the use of the ClientSideXML property.</span></span>  
  
 [<span data-ttu-id="c56f2-117">Exécution de requêtes XPath &#40;fournisseur SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="c56f2-117">Executing XPath Queries &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-xpath-queries-sqlxmloledb-provider.md)  
 <span data-ttu-id="c56f2-118">Illustre l’utilisation des propriétés ClientSideXML, chemin de base et schéma de mappage.</span><span class="sxs-lookup"><span data-stu-id="c56f2-118">Illustrates the use of the ClientSideXML, Base Path, and Mapping Schema properties.</span></span>  
  
 [<span data-ttu-id="c56f2-119">Exécution de requêtes XPath avec des espaces de noms &#40;fournisseur SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="c56f2-119">Executing XPath Queries with Namespaces &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-xpath-queries-with-namespaces-sqlxmloledb-provider.md)  
 <span data-ttu-id="c56f2-120">Illustre la procédure d'interrogation sur des schémas qualifiés par un espace de noms.</span><span class="sxs-lookup"><span data-stu-id="c56f2-120">Illustrates how to query against namespace-qualified schemas.</span></span>  
  
 [<span data-ttu-id="c56f2-121">Exécution de modèles contenant des requêtes XPath &#40;fournisseur SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="c56f2-121">Executing Templates That Contain XPath Queries &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-templates-that-contain-xpath-queries-sqlxmloledb-provider.md)  
 <span data-ttu-id="c56f2-122">Montre comment exécuter des modèles avec des requêtes SQL à l’aide des propriétés ClientSideXML, chemin de base et schéma de mappage.</span><span class="sxs-lookup"><span data-stu-id="c56f2-122">Illustrates how to execute templates with SQL queries using the ClientSideXML, Base Path, and Mapping Schema properties.</span></span>  
  
 [<span data-ttu-id="c56f2-123">Application d’une transformation XSL &#40;fournisseur SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="c56f2-123">Applying an XSL Transformation &#40;SQLXMLOLEDB Provider&#41;</span></span>](applying-an-xsl-transformation-sqlxmloledb-provider.md)  
 <span data-ttu-id="c56f2-124">Illustre l’utilisation des propriétés ClientSideXML et xsl lors de l’application d’une transformation XSL.</span><span class="sxs-lookup"><span data-stu-id="c56f2-124">Illustrates the use of the ClientSideXML and xsl properties in applying an XSL transformation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c56f2-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c56f2-125">See Also</span></span>  
 [<span data-ttu-id="c56f2-126">Configuration requise pour SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="c56f2-126">System Requirements for SQL Server Native Client</span></span>](../../native-client/system-requirements-for-sql-server-native-client.md)  
  
  
