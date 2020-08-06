---
title: Objet SqlXmlAdapter (classes managées SQLXML) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- void Update(DataSet ds) method
- SqlXmlAdapter object
- void Fill(DataSet ds) method
- SQLXML Managed Classes, SqlXmlAdapter object
- Managed Classes [SQLXML], SqlXmlAdapter object
ms.assetid: 0a16eddf-fc26-4d92-82d4-359b5fb905d5
author: rothja
ms.author: jroth
ms.openlocfilehash: 1357ab7d070c7c2e451e31bccfda22c58eac42d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600748"
---
# <a name="sqlxmladapter-object-sqlxml-managed-classes"></a><span data-ttu-id="40659-102">Objet SqlXmlAdapter (classes managées SQLXML)</span><span class="sxs-lookup"><span data-stu-id="40659-102">SqlXmlAdapter Object (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="40659-103">Cet objet fournit des méthodes qui facilitent l'interaction avec le dataset dans le [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="40659-103">This object provides methods that facilitate interaction with the dataset in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span></span> <span data-ttu-id="40659-104">Pour obtenir un exemple fonctionnel, consultez [accès à la fonctionnalité SQLXML dans l’environnement .net](accessing-sqlxml-functionality-in-the-net-environment.md).</span><span class="sxs-lookup"><span data-stu-id="40659-104">For a working sample, see [Accessing SQLXML Functionality in the .NET Environment](accessing-sqlxml-functionality-in-the-net-environment.md).</span></span>  
  
 <span data-ttu-id="40659-105">L’objet SqlXmlAdapter prend en charge les méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="40659-105">The SqlXmlAdapter object supports these methods:</span></span>  
  
 <span data-ttu-id="40659-106">void Fill (DataSet DS)</span><span class="sxs-lookup"><span data-stu-id="40659-106">void Fill(DataSet ds)</span></span>  
 <span data-ttu-id="40659-107">Remplit le dataset dans le .NET Framework avec les données XML extraites de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40659-107">Fills the dataset in the .NET Framework with the XML data retrieved from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="40659-108">annuler la mise à jour (DataSet DS)</span><span class="sxs-lookup"><span data-stu-id="40659-108">void Update(DataSet ds)</span></span>  
 <span data-ttu-id="40659-109">Applique des mises à jour aux enregistrements dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à partir des données dans le dataset.</span><span class="sxs-lookup"><span data-stu-id="40659-109">Applies updates to records in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] from the data in the dataset.</span></span>  
  
 <span data-ttu-id="40659-110">L’objet SqlXmlAdapter prend en charge les constructeurs suivants :</span><span class="sxs-lookup"><span data-stu-id="40659-110">The SqlXmlAdapter object supports these constructors:</span></span>  
  
```  
public SqlXmlAdapter(SqlXmlCommand  cmd)   
  
public SqlXmlAdapter(  
                     string commandText,   
                     SqlXmlCommandType cmdType,   
                     string connectionString  
                      )   
  
public SqlXmlAdapter(  
                     Stream commandStream,   
                     SqlXmlCommandType cmdType,   
                     string connectionString  
                     )   
```  
  
## <a name="see-also"></a><span data-ttu-id="40659-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="40659-111">See Also</span></span>  
 <span data-ttu-id="40659-112">[Objet SqlXmlCommand &#40;les classes managées SQLXML&#41;](sqlxml-4-0-net-framework-support-managed-classes.md) </span><span class="sxs-lookup"><span data-stu-id="40659-112">[SqlXmlCommand Object &#40;SQLXML Managed Classes&#41;](sqlxml-4-0-net-framework-support-managed-classes.md) </span></span>  
 [<span data-ttu-id="40659-113">Objet SqlXmlParameter &#40;les classes managées SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="40659-113">SqlXmlParameter Object &#40;SQLXML Managed Classes&#41;</span></span>](sqlxml-managed-classes-sqlxmlparameter-object.md)  
  
  
