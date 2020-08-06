---
title: Renommer un ordinateur serveur de rapports | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- renaming report servers
ms.assetid: 82fc4ba2-291a-4939-a025-271b8d687c54
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fe8f699c17f9e5f1e11406ac6e5c161488767ed1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614387"
---
# <a name="rename-a-report-server-computer"></a><span data-ttu-id="49770-102">Changement de nom d'un ordinateur serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="49770-102">Rename a Report Server Computer</span></span>
  <span data-ttu-id="49770-103">Le renommage d’un ordinateur entraîne une modification équivalente du nom pour le serveur web et l’instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (si elle se trouve sur le même ordinateur).</span><span class="sxs-lookup"><span data-stu-id="49770-103">Renaming a computer causes a corresponding name change for the Web server and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (if it is on the same computer).</span></span> <span data-ttu-id="49770-104">Dans certains cas, il est possible que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] ne soit pas accessible après la modification du nom d'un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="49770-104">In some cases, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] may not be accessible after a computer name change.</span></span> <span data-ttu-id="49770-105">Suivez les instructions de cette rubrique pour reconfigurer un serveur de rapports après un changement de nom d'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="49770-105">Use the steps provided in this topic to reconfigure a report server after a computer name change.</span></span>  
  
## <a name="renaming-a-sql-server-database-engine"></a><span data-ttu-id="49770-106">Changement de nom d'un moteur de base de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="49770-106">Renaming a SQL Server Database Engine</span></span>  
 <span data-ttu-id="49770-107">Si vous renommez l'instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] qui exécute la base de données du serveur de rapports, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="49770-107">If you rename the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] instance that runs the report server database, do the following:</span></span>  
  
1.  <span data-ttu-id="49770-108">Démarrez l'outil de configuration de Reporting Services et connectez-vous au serveur de rapports qui utilise la base de données de serveur de rapports sur le serveur renommé.</span><span class="sxs-lookup"><span data-stu-id="49770-108">Start the Reporting Services Configuration tool and connect to the report server that uses the report server database on the renamed server.</span></span>  
  
2.  <span data-ttu-id="49770-109">Ouvrez la page Installation de la base de données.</span><span class="sxs-lookup"><span data-stu-id="49770-109">Open the Database Setup page.</span></span>  
  
3.  <span data-ttu-id="49770-110">Dans **Nom du serveur**, tapez ou sélectionnez le nom du serveur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , puis cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="49770-110">In **Server Name**, type or select the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] name, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="49770-111">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="49770-111">Click **Apply**.</span></span>  
  
 <span data-ttu-id="49770-112">Si le serveur de rapports utilise une instance de [!INCLUDE[ssDE](../../includes/ssde-md.md)] locale, vous pouvez utiliser *(local)* ou *(local)\nom_instance* pour spécifier le serveur.</span><span class="sxs-lookup"><span data-stu-id="49770-112">If the report server is using a local [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance, you can use *(local)* or *(local)\instancename* to specify the server.</span></span> <span data-ttu-id="49770-113">Si vous utilisez *(local)* pour faire référence au serveur, vous pourrez renommer le serveur et les connexions continueront à fonctionner.</span><span class="sxs-lookup"><span data-stu-id="49770-113">If you use *(local)* to refer to the server, you can rename the server and the connections will continue to work.</span></span> <span data-ttu-id="49770-114">Si vous utilisez un serveur distant, ou si [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] est configuré à l'aide du nom du serveur, vous devez mettre à jour les informations de connexion à la base de données lorsque le nom du serveur est modifié.</span><span class="sxs-lookup"><span data-stu-id="49770-114">If you are using a remote server, or if [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is configured using the server name, you must update the database connection information whenever the server name is changed.</span></span>  
  
## <a name="renaming-a-report-server-computer"></a><span data-ttu-id="49770-115">Changement de nom d'un ordinateur serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="49770-115">Renaming a Report Server Computer</span></span>  
 <span data-ttu-id="49770-116">Si vous renommez un ordinateur qui exécute un serveur de rapports, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="49770-116">If you rename a computer that runs a report server, do the following:</span></span>  
  
1.  <span data-ttu-id="49770-117">Ouvrez **RSReportServer.config** dans un éditeur de texte et modifiez le `UrlRoot` paramètre pour qu’il reflète le nouveau nom du serveur.</span><span class="sxs-lookup"><span data-stu-id="49770-117">Open **RSReportServer.config** in a text editor and modify the `UrlRoot` setting to reflect the new server name.</span></span> <span data-ttu-id="49770-118">Le paramètre `UrlRoot` est utilisé par les extensions de remise pour composer l'URL permettant d'accéder aux éléments stockés sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="49770-118">The `UrlRoot` setting is used by delivery extensions to compose the URL used to access items stored on the report server.</span></span> <span data-ttu-id="49770-119">Pour changer l'adresse URL du serveur de rapports, vous devez mettre à jour le paramètre `UrlRoot` afin que les abonnements continuent à remettre des rapports comme prévu.</span><span class="sxs-lookup"><span data-stu-id="49770-119">Changing the report server URL address requires that you update the `UrlRoot` setting so that subscriptions continue to deliver reports as expected.</span></span>  
  
2.  <span data-ttu-id="49770-120">Dans le même fichier, s'il est défini, modifiez le paramètre `ReportServerUrl` en fonction du nouveau nom du serveur.</span><span class="sxs-lookup"><span data-stu-id="49770-120">In the same file, if it is set, modify the `ReportServerUrl` setting to reflect the new server name.</span></span> <span data-ttu-id="49770-121">Notez que ce paramètre n'est pas utilisé dans chaque installation.</span><span class="sxs-lookup"><span data-stu-id="49770-121">Note that this setting is not used in every installation.</span></span> <span data-ttu-id="49770-122">S'il est vide, ne faites rien.</span><span class="sxs-lookup"><span data-stu-id="49770-122">If it is empty, do nothing.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="49770-123">Si vous utilisez le service WINS (Windows Internet Naming Service) sur le réseau de votre entreprise, le serveur de rapports et le Gestionnaire de rapports peuvent continuer à être disponibles sous le nom précédent pendant une certaine période de temps.</span><span class="sxs-lookup"><span data-stu-id="49770-123">If you are using Windows Internet Naming Service (WINS) on your corporate network, the report server and Report Manager may continue to be available under the previous name for a period of time.</span></span> <span data-ttu-id="49770-124">WINS mappe une adresse IP à chaque ordinateur qui utilise ce service.</span><span class="sxs-lookup"><span data-stu-id="49770-124">WINS maps an IP address to each computer it services.</span></span> <span data-ttu-id="49770-125">Une fois que WINS a actualisé l'adresse IP pour l'ordinateur renommé, l'ancien nom ne peut plus être utilisé pour accéder à un serveur de rapports ou au Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="49770-125">After WINS refreshes the IP address for the renamed computer, the old computer name can no longer be used to access a report server or Report Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49770-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="49770-126">See Also</span></span>  
 <span data-ttu-id="49770-127">[Fichier de configuration RSReportServer](rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="49770-127">[RSReportServer Configuration File](rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="49770-128">[Gestionnaire de configuration de Reporting Services &#40;mode natif&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="49770-128">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 <span data-ttu-id="49770-129">[Serveur de rapports Reporting Services &#40;mode natif&#41;](reporting-services-report-server-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="49770-129">[Reporting Services Report Server &#40;Native Mode&#41;](reporting-services-report-server-native-mode.md) </span></span>  
 <span data-ttu-id="49770-130">[Démarrer et arrêter le service Report Server](start-and-stop-the-report-server-service.md) </span><span class="sxs-lookup"><span data-stu-id="49770-130">[Start and Stop the Report Server Service](start-and-stop-the-report-server-service.md) </span></span>  
 [<span data-ttu-id="49770-131">Utilitaire rsconfig &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="49770-131">rsconfig Utility &#40;SSRS&#41;</span></span>](../tools/rsconfig-utility-ssrs.md)  
  
  
