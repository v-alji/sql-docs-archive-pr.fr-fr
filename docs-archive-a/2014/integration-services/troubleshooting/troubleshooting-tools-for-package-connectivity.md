---
title: Outils de dépannage connectivité des packages | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Integration Services packages, troubleshooting
- SSIS packages, troubleshooting
- Integration Services, troubleshooting
- connectivity [Integration Services], troubleshooting
- errors [Integration Services], troubleshooting
- packages [Integration Services], troubleshooting
ms.assetid: 08a019f5-8ba7-4527-97c1-e9846d4022ff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1baac9af5a30fdc0f5b15e8ac56eb5badacc0edb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700001"
---
# <a name="troubleshooting-tools-package-connectivity"></a><span data-ttu-id="2c628-102">Outils de dépannage de la connectivité des packages</span><span class="sxs-lookup"><span data-stu-id="2c628-102">Troubleshooting Tools Package Connectivity</span></span>
  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="2c628-103">inclut des fonctionnalités et des outils que vous pouvez utiliser pour dépanner la connectivité entre les packages et les sources de données à partir desquelles les packages extraient et chargent des données.</span><span class="sxs-lookup"><span data-stu-id="2c628-103">includes features and tools that you can use to troubleshoot connectivity between packages and the data sources from which packages extract and load data.</span></span>  
  
## <a name="troubleshooting-issues-with-external-data-providers"></a><span data-ttu-id="2c628-104">Dépannage des problèmes liés aux fournisseurs de données externes</span><span class="sxs-lookup"><span data-stu-id="2c628-104">Troubleshooting Issues with External Data Providers</span></span>  
 <span data-ttu-id="2c628-105">Beaucoup de packages échouent lorsqu'ils communiquent avec des fournisseurs de données externes.</span><span class="sxs-lookup"><span data-stu-id="2c628-105">Many packages fail during interactions with external data providers.</span></span> <span data-ttu-id="2c628-106">Néanmoins, les messages que retournent ces fournisseurs à [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] apportent souvent des informations insuffisantes pour commencer à résoudre cet échec de communication.</span><span class="sxs-lookup"><span data-stu-id="2c628-106">However, the messages that those providers return to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] frequently do not provide enough information to start troubleshooting the interaction.</span></span> <span data-ttu-id="2c628-107">Pour traiter ce problème, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] inclut des messages de journalisation qui vous permettent de résoudre les problèmes d'interaction d'un package avec des sources de données externes.</span><span class="sxs-lookup"><span data-stu-id="2c628-107">To address this troubleshooting need, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes logging messages that you can use to troubleshoot a package's interaction with external data sources.</span></span>  
  
-   <span data-ttu-id="2c628-108">**Activez la journalisation et sélectionnez l’événement Diagnostic du package pour afficher les messages de dépannage**.</span><span class="sxs-lookup"><span data-stu-id="2c628-108">**Enable logging and select the package's Diagnostic event to see the troubleshooting messages**.</span></span> <span data-ttu-id="2c628-109">Les composants [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] suivants peuvent écrire un message dans le journal avant et après chaque appel à un fournisseur de données externes :</span><span class="sxs-lookup"><span data-stu-id="2c628-109">The following [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components are capable of writing a message to the log before and after every call to an external data provider:</span></span>  
  
    -   <span data-ttu-id="2c628-110">Gestionnaire de connexions OLE DB, source OLE DB et destination OLE DB</span><span class="sxs-lookup"><span data-stu-id="2c628-110">OLE DB connection manager, OLE DB source, and OLE DB destination</span></span>  
  
    -   <span data-ttu-id="2c628-111">Gestionnaire de connexions [!INCLUDE[vstecado](../../includes/vstecado-md.md)] et source ADO NET</span><span class="sxs-lookup"><span data-stu-id="2c628-111">[!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager and ADO NET source</span></span>  
  
    -   <span data-ttu-id="2c628-112">Tâche d'exécution de requêtes SQL</span><span class="sxs-lookup"><span data-stu-id="2c628-112">Execute SQL task</span></span>  
  
    -   <span data-ttu-id="2c628-113">Transformation de recherche, transformation de commande OLE DB et transformation de dimension à variation lente</span><span class="sxs-lookup"><span data-stu-id="2c628-113">Lookup transformation, OLE DB Command transformation, and Slowly Changing Dimension transformation</span></span>  
  
     <span data-ttu-id="2c628-114">Les messages de journal contiennent le nom de la méthode appelée.</span><span class="sxs-lookup"><span data-stu-id="2c628-114">The log messages include the name of the method being called.</span></span> <span data-ttu-id="2c628-115">Par exemple, ils peuvent inclure la méthode `Open` d'un objet OLE DB `Connection` ou la méthode `ExecuteNonQuery` d'un objet `Command`.</span><span class="sxs-lookup"><span data-stu-id="2c628-115">For example, these log messages might include the `Open` method of an OLE DB `Connection` object or the `ExecuteNonQuery` method of a `Command` object.</span></span> <span data-ttu-id="2c628-116">Les messages ont le format suivant, où '%1!s!'</span><span class="sxs-lookup"><span data-stu-id="2c628-116">The messages have the following format, where '%1!s!'</span></span> <span data-ttu-id="2c628-117">est un emplacement réservé pour les informations de méthode :</span><span class="sxs-lookup"><span data-stu-id="2c628-117">is a placeholder for the method information:</span></span>  
  
    ```  
    ExternalRequest_pre: The object is ready to make the following external request: '%1!s!'.  
    ExternalRequest_post: '%1!s!'. The external request has completed.  
    ```  
  
     <span data-ttu-id="2c628-118">Pour résoudre les problèmes d’interaction avec le fournisseur de données externes, passez en revue le journal pour savoir si chaque message transmis « avant » (`ExternalRequest_pre` dispose d’un message transmis « après » (`ExternalRequest_post`) correspondant.</span><span class="sxs-lookup"><span data-stu-id="2c628-118">To troubleshoot the interaction with the external data provider, review the log to see whether every "before" message (`ExternalRequest_pre`) has a corresponding "after" message (`ExternalRequest_post`).</span></span> <span data-ttu-id="2c628-119">Si aucun message postérieur correspondant n'existe, vous savez alors que le fournisseur de données externes n'a pas répondu comme prévu.</span><span class="sxs-lookup"><span data-stu-id="2c628-119">If there is no corresponding "after" message, you know that the external data provider did not respond as expected.</span></span>  
  
     <span data-ttu-id="2c628-120">L'exemple suivant présente quelques exemples de lignes d'un journal contenant ces messages de journalisation :</span><span class="sxs-lookup"><span data-stu-id="2c628-120">The following example shows some sample rows from a log that contains these logging messages:</span></span>  
  
    ```  
    ExternalRequest_pre: The object is ready to make the following external request: 'ITransactionJoin::JoinTransaction'.  
    ExternalRequest_post: 'ITransactionJoin::JoinTransaction succeeded'. The external request has completed.  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDbConnection.Open'.  
    ExternalRequest_post: 'IDbConnection.Open succeeded'. The external request has completed.  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDbConnection.CreateCommand'.  
    ExternalRequest_post: 'IDbConnection.CreateCommand finished'. The external request has completed."  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDbCommand.ExecuteReader'.  
    ExternalRequest_post: 'IDbCommand.ExecuteReader finished'. The external request has completed."  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDataReader.GetSchemaTable'.  
    ExternalRequest_post: 'IDataReader.GetSchemaTable finished'. The external request has completed."  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDataReader.Close'.  
    ExternalRequest_post: 'IDataReader.Close finished'. The external request has completed."  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDbConnection.Close'.  
    ExternalRequest_post: 'IDbConnection.Close finished'. The external request has completed."  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2c628-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2c628-121">See Also</span></span>  
 <span data-ttu-id="2c628-122">[Outils de dépannage pour le développement des packages](troubleshooting-tools-for-package-development.md) </span><span class="sxs-lookup"><span data-stu-id="2c628-122">[Troubleshooting Tools for Package Development](troubleshooting-tools-for-package-development.md) </span></span>  
 [<span data-ttu-id="2c628-123">Outils de dépannage pour l’exécution des packages</span><span class="sxs-lookup"><span data-stu-id="2c628-123">Troubleshooting Tools for Package Execution</span></span>](troubleshooting-tools-for-package-execution.md)  
  
  
