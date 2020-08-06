---
title: Procédures stockées système XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- system stored procedures [SQL Server], XML
- sp_xml_removedocument
- OPENXML statement, system stored procedures
- sp_xml_preparedocument
- XML [SQL Server], system stored procedures
ms.assetid: e60c7f85-6823-4d28-93d6-b053d08cc830
author: rothja
ms.author: jroth
ms.openlocfilehash: 2008294fe5bc532dfb6883656420b4189e4da7b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611626"
---
# <a name="xml-system-stored-procedures"></a><span data-ttu-id="e0786-102">Procédures stockées système XML</span><span class="sxs-lookup"><span data-stu-id="e0786-102">XML System Stored Procedures</span></span>
  <span data-ttu-id="e0786-103">SQL Server propose les procédures stockées système suivantes utilisées en conjonction avec la clause OPENXML :</span><span class="sxs-lookup"><span data-stu-id="e0786-103">SQL Server provides the following system stored procedures that are used together with OPENXML:</span></span>  
  
-   [<span data-ttu-id="e0786-104">sp_xml_preparedocument &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e0786-104">sp_xml_preparedocument &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-xml-preparedocument-transact-sql)  
  
-   [<span data-ttu-id="e0786-105">sp_xml_removedocument &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e0786-105">sp_xml_removedocument &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-xml-removedocument-transact-sql)  
  
 <span data-ttu-id="e0786-106">Pour écrire des requêtes à l’aide d’OPENXML, vous devez d’abord créer une représentation interne du document XML en appelant **sp_xml_preparedocument**.</span><span class="sxs-lookup"><span data-stu-id="e0786-106">To write queries by using OPENXML, you must first create an internal representation of the XML document by calling **sp_xml_preparedocument**.</span></span> <span data-ttu-id="e0786-107">Celle-ci renvoie un descripteur vers la représentation interne du document XML.</span><span class="sxs-lookup"><span data-stu-id="e0786-107">The stored procedure returns a handle to the internal representation of the XML document.</span></span> <span data-ttu-id="e0786-108">Ce descripteur est ensuite transmis à OPENXML.</span><span class="sxs-lookup"><span data-stu-id="e0786-108">This handle is then passed to OPENXML.</span></span> <span data-ttu-id="e0786-109">OPENXML fournit des vues sur les ensembles de lignes du document s'appuyant sur des chemins XPaths.</span><span class="sxs-lookup"><span data-stu-id="e0786-109">OPENXML provides rowset views of the document based on XPaths.</span></span> <span data-ttu-id="e0786-110">Plus précisément, ces vues correspondent à un modèle de ligne et à un ou plusieurs modèles de colonnes.</span><span class="sxs-lookup"><span data-stu-id="e0786-110">Specifically, this is one row pattern and one or more column patterns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e0786-111">Le descripteur du document renvoyé par **sp_xml_preparedocument** reste valide pendant toute la durée de la session.</span><span class="sxs-lookup"><span data-stu-id="e0786-111">The document handle that is returned by **sp_xml_preparedocument** is valid for the duration of the session.</span></span>  
  
 <span data-ttu-id="e0786-112">Vous pouvez supprimer la représentation interne d’un document XML de la mémoire en appelant la procédure stockée système **sp_xml_removedocument** .</span><span class="sxs-lookup"><span data-stu-id="e0786-112">The internal representation of an XML document can be removed from memory by calling the **sp_xml_removedocument** system stored procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0786-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e0786-113">See Also</span></span>  
 <span data-ttu-id="e0786-114">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e0786-114">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span></span>  
 [<span data-ttu-id="e0786-115">OPENXML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e0786-115">OPENXML &#40;SQL Server&#41;</span></span>](../xml/openxml-sql-server.md)  
  
  
