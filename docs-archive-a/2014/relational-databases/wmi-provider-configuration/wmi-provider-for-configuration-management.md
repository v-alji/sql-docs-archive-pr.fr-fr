---
title: Fournisseur WMI pour les concepts de gestion de configuration | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- WMI Provider for Configuration Management
- SQL Server WMI Provider
- configuration management [WMI]
- WMI Provider for Configuration Management, about WMI Provider for Configuration Management
ms.assetid: 7e41db24-b915-4eb8-a1d6-e6948ee915b7
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: be0682e7d6de5cb8c3d67a2f300bb89122213652
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603321"
---
# <a name="wmi-provider-for-configuration-management-concepts"></a><span data-ttu-id="59997-102">Fournisseur WMI pour les concepts de gestion de configuration</span><span class="sxs-lookup"><span data-stu-id="59997-102">WMI Provider for Configuration Management Concepts</span></span>
  <span data-ttu-id="59997-103">Le fournisseur WMI est une couche publiée qui est utilisée avec le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] composant logiciel enfichable Configuration Manager pour [!INCLUDE[msCoName](../../includes/msconame-md.md)] la console MMC (Management Console) et le [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="59997-103">The WMI provider is a published layer that is used with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager snap-in for [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console (MMC) and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="59997-104">Il offre une méthode d'interface unifiée avec les appels API qui gèrent les opérations de registre requises par le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Il permet également un contrôle et une manipulation avancés des services [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="59997-104">It provides a unified way for interfacing with the API calls that manage the registry operations requested by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager and provides enhanced control and manipulation over the selected [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services.</span></span>  
  
 <span data-ttu-id="59997-105">Le fournisseur WMI [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se compose d'une DLL et d'un fichier MOF, compilés automatiquement par le programme d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59997-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] WMI Provider is a DLL and a MOF file, which are compiled automatically by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup.</span></span>  
  
 <span data-ttu-id="59997-106">Le fournisseur WMI [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contient un jeu de classes d'objets utilisé pour contrôler les services [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="59997-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] WMI Provider contains a set of object classes used to control the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services using the following methods:</span></span>  
  
-   <span data-ttu-id="59997-107">Langage de script tel que VBScript, [!INCLUDE[jsprjscript](../../includes/jsprjscript-md.md)] ou Perl, dans lequel le langage WQL (Windows Query Language) peut être incorporé.</span><span class="sxs-lookup"><span data-stu-id="59997-107">A script language such as VBScript, [!INCLUDE[jsprjscript](../../includes/jsprjscript-md.md)], or Perl, in which Windows Query Language (WQL) can be embedded.</span></span>  
  
-   <span data-ttu-id="59997-108">Objet <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> d'un programme de code managé SMO.</span><span class="sxs-lookup"><span data-stu-id="59997-108">The <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> object in an SMO managed code program.</span></span>  
  
-   <span data-ttu-id="59997-109">Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou MMC avec le composant logiciel enfichable du fournisseur WMI de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59997-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager or MMC with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] WMI provider snap-in.</span></span>  
  
## <a name="using-a-script-language"></a><span data-ttu-id="59997-110">Utilisation d'un langage de script</span><span class="sxs-lookup"><span data-stu-id="59997-110">Using a Script Language</span></span>  
 <span data-ttu-id="59997-111">Les avantages de l'utilisation d'un langage de script sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="59997-111">The advantages of using a script language include the following:</span></span>  
  
-   <span data-ttu-id="59997-112">Environnement de développement non obligatoire.</span><span class="sxs-lookup"><span data-stu-id="59997-112">A development environment is not required.</span></span>  
  
-   <span data-ttu-id="59997-113">Vaste disponibilité des fichiers qui prennent en charge le langage de script.</span><span class="sxs-lookup"><span data-stu-id="59997-113">The files that support the script language are widely available.</span></span>  
  
 <span data-ttu-id="59997-114">Le script peut également fonctionner avec d'autres fournisseurs WMI en plus du fournisseur WMI [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59997-114">The script can also work with other WMI Providers in addition to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] WMI Provider.</span></span> <span data-ttu-id="59997-115">Un administrateur de domaine peut utiliser un script pour installer les services, les paramètres réseau et les paramètres d'alias sur plusieurs ordinateurs d'un réseau.</span><span class="sxs-lookup"><span data-stu-id="59997-115">A domain administrator can use a script to set up the services, network settings, and alias settings on multiple computers on a network.</span></span>  
  
 <span data-ttu-id="59997-116">Cette section traite plus en détail de l'accès au fournisseur WMI de la gestion de la configuration à partir de scripts.</span><span class="sxs-lookup"><span data-stu-id="59997-116">This section deals with accessing the WMI Provider for Configuration Management from scripts in further detail.</span></span>  
  
## <a name="using-the-smo-managedcomputer-object"></a><span data-ttu-id="59997-117">Utilisation de l'objet SMO ManagedComputer</span><span class="sxs-lookup"><span data-stu-id="59997-117">Using the SMO ManagedComputer Object</span></span>  
 <span data-ttu-id="59997-118">L'objet <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> est un objet SMO managé qui fournit l'accès au fournisseur WMI de la gestion de la configuration.</span><span class="sxs-lookup"><span data-stu-id="59997-118">The <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> object is a managed SMO object that provides access to the WMI Provider for Configuration Management.</span></span> <span data-ttu-id="59997-119">En utilisant un programme SMO, l'objet <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> peut être utilisé pour afficher et modifier les services [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], les paramètres réseau et les paramètres d'alias.</span><span class="sxs-lookup"><span data-stu-id="59997-119">By using an SMO program, the <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> object can be used to view and modify [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, network settings, and alias settings.</span></span> <span data-ttu-id="59997-120">Pour plus d’informations, consultez [gestion des services et des paramètres réseau à l’aide du fournisseur WMI](../server-management-objects-smo/tasks/managing-services-and-network-settings-by-using-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="59997-120">For more information, see [Managing Services and Network Settings by Using WMI Provider](../server-management-objects-smo/tasks/managing-services-and-network-settings-by-using-wmi-provider.md).</span></span>  
  
## <a name="using-the-microsoft-management-console-or-sql-server-configuration-manager"></a><span data-ttu-id="59997-121">Utilisation de la console MMC (Microsoft Management Console) ou du Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="59997-121">Using the Microsoft Management Console or SQL Server Configuration Manager</span></span>  
 <span data-ttu-id="59997-122">La console MMC fournit une interface pour gérer les services [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], par opposition à un langage de script ou à un programme de code managé.</span><span class="sxs-lookup"><span data-stu-id="59997-122">Microsoft Management Console (MMC) provides an interface to manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, as opposed to a scripting language or managed code program.</span></span> <span data-ttu-id="59997-123">Le composant logiciel enfichable MMC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management peut être utilisé pour arrêter ou démarrer les services, et pour modifier les comptes de service.</span><span class="sxs-lookup"><span data-stu-id="59997-123">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management MMC snap-in can be used to stop and start services, and to change service accounts.</span></span>  
  
 <span data-ttu-id="59997-124">Le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permet aussi de gérer les services [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], les protocoles client et serveur, et les alias serveur.</span><span class="sxs-lookup"><span data-stu-id="59997-124">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager can also be used to manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, client and server protocols, and server aliases</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59997-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="59997-125">See Also</span></span>  
 <span data-ttu-id="59997-126">[Comprendre le fournisseur WMI pour la gestion de la configuration](understanding-the-wmi-provider-for-configuration-management.md) </span><span class="sxs-lookup"><span data-stu-id="59997-126">[Understanding the WMI Provider for Configuration Management](understanding-the-wmi-provider-for-configuration-management.md) </span></span>  
 <span data-ttu-id="59997-127">[Utilisation du fournisseur WMI pour la gestion de la configuration](working-with-the-wmi-provider-for-configuration-management.md) </span><span class="sxs-lookup"><span data-stu-id="59997-127">[Working with the WMI Provider for Configuration Management](working-with-the-wmi-provider-for-configuration-management.md) </span></span>  
 [<span data-ttu-id="59997-128">Utilisation des langages WQL et de script avec le fournisseur WMI pour la gestion de configuration</span><span class="sxs-lookup"><span data-stu-id="59997-128">Using WQL and Scripting Languages with the WMI Provider for Configuration Management</span></span>](using-wql-and-scripting-languages-with-the-wmi-provider.md)  
  
  
