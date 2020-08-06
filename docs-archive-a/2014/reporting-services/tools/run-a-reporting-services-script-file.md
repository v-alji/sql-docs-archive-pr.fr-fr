---
title: Exécuter un fichier de script Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- scripts [Reporting Services], running
ms.assetid: 0de4995c-85ec-4d4c-aaef-fbd30edfb20f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c787d860838a57a2bd0f51aac1e9159833f038d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704808"
---
# <a name="run-a-reporting-services-script-file"></a><span data-ttu-id="5d419-102">Exécuter un fichier de script Reporting Services</span><span class="sxs-lookup"><span data-stu-id="5d419-102">Run a Reporting Services Script File</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="5d419-103">Les fichiers de script sont exécutés à partir de l’invite de commandes à l’aide de l’environnement de script [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] (RS.exe).</span><span class="sxs-lookup"><span data-stu-id="5d419-103">script files are run from the command prompt using the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] script environment (RS.exe).</span></span> <span data-ttu-id="5d419-104">RS.exe possède de nombreux arguments d'invite de commandes que vous pouvez utiliser.</span><span class="sxs-lookup"><span data-stu-id="5d419-104">RS.exe has many command prompt arguments available for you to use.</span></span> <span data-ttu-id="5d419-105">Pour plus d’informations sur les options d’invite de commandes, consultez [Utilitaire RS.exe &#40;SSRS&#41;](rs-exe-utility-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5d419-105">For more information about the command prompt options, see [RS.exe Utility &#40;SSRS&#41;](rs-exe-utility-ssrs.md).</span></span> <span data-ttu-id="5d419-106">Pour d’autres exemples de scripts, consultez [Exemples de produit SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="5d419-106">For more script samples, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="sample-command-lines"></a><span data-ttu-id="5d419-107">Exemples de lignes de commande</span><span class="sxs-lookup"><span data-stu-id="5d419-107">Sample Command Lines</span></span>  
  
-   <span data-ttu-id="5d419-108">Exécutez Script.rss dans l'environnement de script qui désigne le serveur de rapports cible.</span><span class="sxs-lookup"><span data-stu-id="5d419-108">Run Script.rss in the script environment designating the target report server.</span></span> <span data-ttu-id="5d419-109">L'authentification Windows est appliquée par défaut :</span><span class="sxs-lookup"><span data-stu-id="5d419-109">Windows Authentication is applied by default:</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver  
    ```  
  
-   <span data-ttu-id="5d419-110">Exécutez Script.rss dans l'environnement de script en spécifiant un nom d'utilisateur et un mot de passe pour authentifier les appels de service Web :</span><span class="sxs-lookup"><span data-stu-id="5d419-110">Run Script.rss in the script environment specifying a user name and password for authenticating the Web service calls:</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver -u myusername -p mypassword  
    ```  
  
-   <span data-ttu-id="5d419-111">Exécutez Script.rss dans l'environnement de script en spécifiant un délai d'expiration de serveur égal à 30 secondes :</span><span class="sxs-lookup"><span data-stu-id="5d419-111">Run Script.rss in the script environment specifying a server time-out of 30 seconds:</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver -l 30  
    ```  
  
-   <span data-ttu-id="5d419-112">Exécutez Script.rss dans l’environnement de script en spécifiant une variable de script globale appelée *report*.</span><span class="sxs-lookup"><span data-stu-id="5d419-112">Run Script.rss in the script environment specifying a global script variable called *report*.</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver -v report="Company Sales"  
    ```  
  
-   <span data-ttu-id="5d419-113">Exécutez Script.rss dans l'environnement de script en spécifiant que les opérations de service Web du fichier de script s'exécutent en tant que lot.</span><span class="sxs-lookup"><span data-stu-id="5d419-113">Run Script.rss in the script environment specifying that the Web service operations in the script file are run as a batch.</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver -b  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5d419-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5d419-114">See Also</span></span>  
 [<span data-ttu-id="5d419-115">Informations techniques de référence &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5d419-115">Technical Reference &#40;SSRS&#41;</span></span>](../technical-reference-ssrs.md)  
  
  
