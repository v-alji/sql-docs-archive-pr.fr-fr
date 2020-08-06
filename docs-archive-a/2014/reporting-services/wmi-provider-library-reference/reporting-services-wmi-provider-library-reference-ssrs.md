---
title: Référence de bibliothèque du fournisseur WMI de Reporting Services (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- Reporting Services WMI Provider Library
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- WMI provider [Reporting Services], library
ms.assetid: 17ba711d-7eff-4423-9168-63dc425a3428
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2a98ca22f9d34627e484a698dcf540b31808d07e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604340"
---
# <a name="reporting-services-wmi-provider-library-reference-ssrs"></a><span data-ttu-id="bfe5f-102">Référence de bibliothèque du fournisseur WMI de Reporting Services (SSRS)</span><span class="sxs-lookup"><span data-stu-id="bfe5f-102">Reporting Services WMI Provider Library Reference (SSRS)</span></span>
  <span data-ttu-id="bfe5f-103">Le fournisseur [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Windows Management Instrumentation (WMI) prend en charge des opérations WMI qui vous permettent d’écrire des scripts et du code pour modifier des paramètres du serveur de rapports et du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="bfe5f-103">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Windows Management Instrumentation (WMI) provider supports WMI operations that enable you to write scripts and code to modify settings of the report server and Report Manager.</span></span>  
  
 <span data-ttu-id="bfe5f-104">Par exemple, si vous voulez spécifier que la sécurité intégrée est utilisée quand le serveur de rapports se connecte à la base de données du serveur de rapports, créez une instance de la classe MSReportServer_ConfigurationSetting et utilisez la propriété DatabaseIntegratedSecurity de l’instance de serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="bfe5f-104">For example, if you want to change whether integrated security is used when the report server connects to the report server database, create an instance of the MSReportServer_ConfigurationSetting class and use the DatabaseIntegratedSecurity property of the of the report server instance.</span></span> <span data-ttu-id="bfe5f-105">Les classes répertoriées dans le tableau suivant représentent des composants [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bfe5f-105">The classes shown in the following table represent [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] components.</span></span> <span data-ttu-id="bfe5f-106">Les classes sont définies dans l’espace de noms [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)] ou [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bfe5f-106">The classes are defined in either the [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)] or the [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)] namespaces.</span></span> <span data-ttu-id="bfe5f-107">Chacune des classes prend en charge des opérations en lecture et en écriture.</span><span class="sxs-lookup"><span data-stu-id="bfe5f-107">Each of the classes support read and write operations.</span></span> <span data-ttu-id="bfe5f-108">Les opérations de création ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="bfe5f-108">Create operations are not supported.</span></span>  
  
## <a name="classes"></a><span data-ttu-id="bfe5f-109">Classes</span><span class="sxs-lookup"><span data-stu-id="bfe5f-109">Classes</span></span>  
 [<span data-ttu-id="bfe5f-110">classe MSReportServer_Instance</span><span class="sxs-lookup"><span data-stu-id="bfe5f-110">MSReportServer_Instance Class</span></span>](msreportserver-instance-class.md)  
 <span data-ttu-id="bfe5f-111">Fournit les informations de base nécessaires à un client pour établir la connexion à un serveur de rapports installé.</span><span class="sxs-lookup"><span data-stu-id="bfe5f-111">Provides basic information required for a client to connect to an installed report server.</span></span>  
  
 [<span data-ttu-id="bfe5f-112">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="bfe5f-112">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
 <span data-ttu-id="bfe5f-113">Représente les paramètres d'installation et d'exécution d'une instance de serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="bfe5f-113">Represents the installation and run-time parameters of a report server instance.</span></span> <span data-ttu-id="bfe5f-114">Ces paramètres sont stockés dans le fichier de configuration du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="bfe5f-114">These parameters are stored in the configuration file for the report server.</span></span>  
  
 <span data-ttu-id="bfe5f-115">Pour plus d’informations sur les opérations WMI, consultez la documentation du SDK WMI inclus dans le [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Kit de développement logiciel (SDK).</span><span class="sxs-lookup"><span data-stu-id="bfe5f-115">For more information about WMI operations, see the WMI SDK documentation included with the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfe5f-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bfe5f-116">See Also</span></span>  
 <span data-ttu-id="bfe5f-117">[Accéder au fournisseur WMI Reporting Services](../tools/access-the-reporting-services-wmi-provider.md) </span><span class="sxs-lookup"><span data-stu-id="bfe5f-117">[Access the Reporting Services WMI Provider](../tools/access-the-reporting-services-wmi-provider.md) </span></span>  
 [<span data-ttu-id="bfe5f-118">Informations techniques de référence &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bfe5f-118">Technical Reference &#40;SSRS&#41;</span></span>](../technical-reference-ssrs.md)  
  
  
