---
title: rsModelGenerationError - Erreur Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsModelGenerationError
ms.assetid: 3a0ad63f-87f9-4ca1-b0c2-c85fa991634a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 713de57f0f2957983966f8ef0345bb374c311781
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605907"
---
# <a name="rsmodelgenerationerror---reporting-services-error"></a><span data-ttu-id="c53d4-102">rsModelGenerationError - Erreur Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c53d4-102">rsModelGenerationError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="c53d4-103">Détails</span><span class="sxs-lookup"><span data-stu-id="c53d4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c53d4-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="c53d4-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="c53d4-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="c53d4-105">Event ID</span></span>|<span data-ttu-id="c53d4-106">rsRenderingError</span><span class="sxs-lookup"><span data-stu-id="c53d4-106">rsRenderingError</span></span>|  
|<span data-ttu-id="c53d4-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="c53d4-107">Event Source</span></span>|<span data-ttu-id="c53d4-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span><span class="sxs-lookup"><span data-stu-id="c53d4-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span></span>|  
|<span data-ttu-id="c53d4-109">Composant</span><span class="sxs-lookup"><span data-stu-id="c53d4-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="c53d4-110">Texte du message</span><span class="sxs-lookup"><span data-stu-id="c53d4-110">Message Text</span></span>|<span data-ttu-id="c53d4-111">Une erreur s'est produite lors de la génération du modèle.</span><span class="sxs-lookup"><span data-stu-id="c53d4-111">An error occurred while generating model.</span></span> <span data-ttu-id="c53d4-112">(rsModelGenerationError) (ReportingServicesLibrary) %1</span><span class="sxs-lookup"><span data-stu-id="c53d4-112">(rsModelGenerationError) (ReportingServicesLibrary) %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c53d4-113">Explication</span><span class="sxs-lookup"><span data-stu-id="c53d4-113">Explanation</span></span>  
 <span data-ttu-id="c53d4-114">Le modèle de rapport n'a pas pu être généré.</span><span class="sxs-lookup"><span data-stu-id="c53d4-114">The report model could not be generated.</span></span> <span data-ttu-id="c53d4-115">Dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]2005 SP1 et les versions antérieures, cette erreur s'affiche, en règle générale, si l'objet System.Data.DataSet ne peut pas gérer une table ou une relation au sein du schéma de la base de données, par exemple lorsque deux clés étrangères sont définies sur la même colonne d'une table.</span><span class="sxs-lookup"><span data-stu-id="c53d4-115">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]2005 SP1 and earlier versions, this error is most likely displayed when the System.Data.DataSet object cannot handle a table or relationship within the database schema, such as when, for example, two foreign keys are defined on the same column within a table.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c53d4-116">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="c53d4-116">User Action</span></span>  
 <span data-ttu-id="c53d4-117">Pour déterminer précisément la raison pour laquelle vous avez reçu ce message, consultez les fichiers journaux du serveur de rapports qui se trouvent dans le dossier \Microsoft SQL Server\\<Instance SQL Server\>\Reporting Services\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="c53d4-117">To determine the specific reason that caused this message to appear, review the report server log files, which are located at \Microsoft SQL Server\\<SQL Server Instance\>\Reporting Services\LogFiles.</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="c53d4-118">Interne uniquement</span><span class="sxs-lookup"><span data-stu-id="c53d4-118">Internal-Only</span></span>  
  
