---
title: Concepts de programmation SQLXML 4,0 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, about SQLXML
- SQLXML
ms.assetid: 5a11cda2-b8a3-4453-848f-641afdaa7024
author: rothja
ms.author: jroth
ms.openlocfilehash: 90a383d2a12e073f262d24a94abe1b094509713c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611660"
---
# <a name="sqlxml-40-programming-concepts"></a><span data-ttu-id="dd110-102">Concepts de la programmation SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="dd110-102">SQLXML 4.0 Programming Concepts</span></span>
  <span data-ttu-id="dd110-103">SQLXML 3.0 a été proposé comme version Web pour fournir des fonctionnalités XML côté client supplémentaires et des améliorations aux fonctionnalités existantes, telles que les schémas XSD annotés, le chargement XML en masse, la prise en charge des services Web (SOAP) et les codes de mise à jour (updategram).</span><span class="sxs-lookup"><span data-stu-id="dd110-103">SQLXML 3.0 was offered as a Web release to provide additional client-side XML functionality and enhancements to existing features, such as annotated XSD schemas, XML bulk load, Web services (SOAP) support, and updategrams.</span></span>  
  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="dd110-104">a introduit SQLXML 4.0, qui offre les mêmes fonctionnalités que SQLXML 3.0, ainsi que des mises à jour supplémentaires afin de gérer les nouvelles fonctionnalités introduites avec [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd110-104">introduced SQLXML 4.0, which continues to deliver the same functionality as SQLXML 3.0 plus additional updates provided to accommodate new features introduced with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="dd110-105">Cette section fournit des informations sur SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="dd110-105">This section provides information about SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="dd110-106">SQLXML n'est pas installé dans SQL Server</span><span class="sxs-lookup"><span data-stu-id="dd110-106">SQLXML Is Not Installed in SQL Server</span></span>](sqlxml-is-not-installed-in-sql-server.md)  
 <span data-ttu-id="dd110-107">Décrit comment installer SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="dd110-107">Describes how to install SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="dd110-108">Nouveautés de SQLXML 4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="dd110-108">What's New in SQLXML 4.0 SP1</span></span>](what-s-new-in-sqlxml-4-0-sp1.md)  
 <span data-ttu-id="dd110-109">Décrit les mises à jour et les améliorations de SQLXML 4.0 et fournit des liens vers les rubriques appropriées de cette documentation.</span><span class="sxs-lookup"><span data-stu-id="dd110-109">Describes the updates and enhancements in SQLXML 4.0, and provides links to relevant topics in this documentation.</span></span>  
  
 [<span data-ttu-id="dd110-110">Utilisation d'ADO pour exécuter des requêtes SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="dd110-110">Using ADO to Execute SQLXML 4.0 Queries</span></span>](using-ado-to-execute-sqlxml-4-0-queries.md)  
 <span data-ttu-id="dd110-111">Décrit comment utiliser ADO pour les requêtes SQLXML.</span><span class="sxs-lookup"><span data-stu-id="dd110-111">Describes how to use ADO for SQLXML queries.</span></span> <span data-ttu-id="dd110-112">ADO joue un rôle plus important dans SQLXML 4.0 que dans les versions antérieures.</span><span class="sxs-lookup"><span data-stu-id="dd110-112">ADO is more prominent in SQLXML 4.0 than in previous versions.</span></span>  
  
 [<span data-ttu-id="dd110-113">Prise en charge du type de données xml dans SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="dd110-113">xml Data Type Support in SQLXML 4.0</span></span>](xml-data-type-support-in-sqlxml-4-0.md)  
 <span data-ttu-id="dd110-114">Décrit la prise en charge du type de données xml ajouté dans SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="dd110-114">Describes the support for the xml data type that has been added for SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="dd110-115">Configuration requise pour l'exécution des exemples SQLXML</span><span class="sxs-lookup"><span data-stu-id="dd110-115">Requirements for Running SQLXML Examples</span></span>](requirements-for-running-sqlxml-examples.md)  
 <span data-ttu-id="dd110-116">Décrit les spécifications permettant de créer des exemples fonctionnels à partir des exemples SQLXML fournis.</span><span class="sxs-lookup"><span data-stu-id="dd110-116">Describe the requirements for creating working samples from the SQLXML examples provided.</span></span>  
  
 [<span data-ttu-id="dd110-117">Mise en forme côté client et côté serveur &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="dd110-117">Client-side and Server-side Formatting &#40;SQLXML 4.0&#41;</span></span>](formatting/client-side-and-server-side-formatting-sqlxml-4-0.md)  
 <span data-ttu-id="dd110-118">Fournit des informations du type « à propos de » et des comparaisons sur la mise en forme côté client et côté serveur, y compris la commande FOR XML permettant de construire des documents XML.</span><span class="sxs-lookup"><span data-stu-id="dd110-118">Provides information about and comparisons of client-side and server-side formatting, including the FOR XML command for constructing XML documents.</span></span>  
  
 [<span data-ttu-id="dd110-119">Schémas XSD annotés dans SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="dd110-119">Annotated XSD Schemas in SQLXML 4.0</span></span>](annotated-xsd-schemas/annotated-xsd-schemas-in-sqlxml-4-0.md)  
 <span data-ttu-id="dd110-120">Fournit des informations sur l'utilisation des schémas XSD annotés dans SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="dd110-120">Provides information about using annotated XSD schemas in SQLXML 4.0.</span></span> <span data-ttu-id="dd110-121">Fournit aussi des informations sur les schémas XDR annotés pour une utilisation dans les applications héritées.</span><span class="sxs-lookup"><span data-stu-id="dd110-121">Also provides information about annotated XDR schemas for use in legacy applications.</span></span>  
  
 [<span data-ttu-id="dd110-122">Utilisation des requêtes XPath dans SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="dd110-122">Using XPath Queries in SQLXML 4.0</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/using-xpath-queries-in-sqlxml-4-0.md)  
 <span data-ttu-id="dd110-123">Décrit comment utiliser un sous-ensemble du langage XPath pour interroger les vues XML créées par un schéma XSD annoté, et fournit des exemples.</span><span class="sxs-lookup"><span data-stu-id="dd110-123">Describes how to use a subset of the XPath language to query the XML views created by an annotated XSD schema, and provides examples.</span></span>  
  
 [<span data-ttu-id="dd110-124">Utilisation de codes de mise à jour (updategrams) pour modifier des données dans SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="dd110-124">Using Updategrams to Modify Data in SQLXML 4.0</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/using-updategrams-to-modify-data-in-sqlxml-4-0.md)  
 <span data-ttu-id="dd110-125">Fournit des informations sur les codes de mise à jour (updategram), qui modifient les données d'une base de données en travaillant sur les vues XML fournies par les schémas XSD (ou XDR) annotés.</span><span class="sxs-lookup"><span data-stu-id="dd110-125">Provides information about updategrams, which modify data in a database by working against the XML views provided by XSD (or XDR) annotated schemas.</span></span>  
  
 [<span data-ttu-id="dd110-126">Exécution du chargement en masse de données XML &#40;SQLXML 4.0&#41;</span><span class="sxs-lookup"><span data-stu-id="dd110-126">Performing Bulk Load of XML Data &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md)  
 <span data-ttu-id="dd110-127">Décrit comment charger en masse XML dans SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="dd110-127">Describes how to bulk load XML in SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="dd110-128">Composants d'accès aux données SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="dd110-128">SQLXML 4.0 Data Access Components</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/data-access-components-provider/sqlxml-4-0-data-access-components-sqlxmloledb-provider.md)  
 <span data-ttu-id="dd110-129">Documente le fournisseur SQLXMLOLEDB et fournit des liens vers d'autre composants d'accès aux données SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="dd110-129">Documents the SQLXMLOLEDB Provider and provides links to other SQLXML 4.0 data access components.</span></span>  
  
 [<span data-ttu-id="dd110-130">Prise en charge de SQLXML 4.0 pour Microsoft .NET Framework</span><span class="sxs-lookup"><span data-stu-id="dd110-130">SQLXML 4.0 .NET Framework Support</span></span>](../../database-engine/dev-guide/sqlxml-4-0-net-framework-support.md)  
 <span data-ttu-id="dd110-131">Décrit la prise en charge de SQLXML 4.0 pour le .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dd110-131">Describes the SQLXML 4.0 support for the .NET Framework.</span></span>  
  
 [<span data-ttu-id="dd110-132">Mise en cache des modèles, XSL et schémas &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="dd110-132">Caching Templates, XSL, and Schemas &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/caching-templates-xml-schemas/caching-templates-xsl-and-schemas-sqlxml-4-0.md)  
 <span data-ttu-id="dd110-133">Décrit les fonctionnalités de mise en cache fournies dans SQLXML pour améliorer les performances.</span><span class="sxs-lookup"><span data-stu-id="dd110-133">Describes the caching functionality provided in SQLXML to improve performance.</span></span>  
  
 [<span data-ttu-id="dd110-134">Considérations relatives à la sécurité SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="dd110-134">SQLXML 4.0 Security Considerations</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/security/sqlxml-4-0-security-considerations.md)  
 <span data-ttu-id="dd110-135">Traite les problèmes de sécurité relatifs à SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="dd110-135">Discusses security issues relevant to SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="dd110-136">Recommandations et limitations de SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="dd110-136">Guidelines and Limitations of SQLXML 4.0</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/guidelines-and-limitations-of-sqlxml-4-0.md)  
 <span data-ttu-id="dd110-137">Répertorie les problèmes à se rappeler lors de l'utilisation de SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="dd110-137">Lists issues to remember when working with SQLXML 4.0.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd110-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dd110-138">See Also</span></span>  
 [<span data-ttu-id="dd110-139">Données XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dd110-139">XML Data &#40;SQL Server&#41;</span></span>](../xml/xml-data-sql-server.md)  
  
  
