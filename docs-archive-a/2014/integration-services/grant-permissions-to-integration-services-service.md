---
title: Accorder des autorisations à Integration Services service | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 0c2caa68-7834-4ea0-bd77-4f3a7c86d634
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0e7ab0c2f482e5a0b1bfeaa06f38ec5a886420a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601583"
---
# <a name="grant-permissions-to-integration-services-service"></a><span data-ttu-id="fe726-102">Accorder des autorisations au service Integration Services</span><span class="sxs-lookup"><span data-stu-id="fe726-102">Grant Permissions to Integration Services Service</span></span>
  <span data-ttu-id="fe726-103">Dans les versions précédentes de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], par défaut, lorsque vous installiez [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , tous les utilisateurs du groupe Utilisateurs avaient accès au service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fe726-103">In previous versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], by default when you installed [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] all users in the Users group had access to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="fe726-104">Lorsque vous installez la version actuelle de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], les utilisateurs n'ont pas accès au service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fe726-104">When you install the current release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], users do not have access to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="fe726-105">Ce service est sécurisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="fe726-105">The service is secure by default.</span></span> <span data-ttu-id="fe726-106">Une fois [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] installé, l'administrateur doit accorder l'accès au service.</span><span class="sxs-lookup"><span data-stu-id="fe726-106">After [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is installed, the administrator must grant access to the service.</span></span>  
  
### <a name="to-grant-access-to-the-integration-services-service"></a><span data-ttu-id="fe726-107">Pour accorder l'accès au service Integration Services</span><span class="sxs-lookup"><span data-stu-id="fe726-107">To grant access to the Integration Services service</span></span>  
  
1.  <span data-ttu-id="fe726-108">Exécutez Dcomcnfg.exe.</span><span class="sxs-lookup"><span data-stu-id="fe726-108">Run Dcomcnfg.exe.</span></span> <span data-ttu-id="fe726-109">Dcomcnfg.exe fournit une interface utilisateur qui permet de modifier certains paramètres du Registre.</span><span class="sxs-lookup"><span data-stu-id="fe726-109">Dcomcnfg.exe provides a user interface for modifying certain settings in the registry.</span></span>  
  
2.  <span data-ttu-id="fe726-110">Dans la boîte de dialogue **Services de composants**, développez le nœud Services de composants > Ordinateurs > Poste de travail > Configuration DCOM.</span><span class="sxs-lookup"><span data-stu-id="fe726-110">In the **Component Services** dialog, expand the Component Services > Computers > My Computer > DCOM Config node.</span></span>  
  
3.  <span data-ttu-id="fe726-111">Cliquez avec le bouton droit sur **Microsoft SQL Server Integration Services 12,0**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="fe726-111">Right-click **Microsoft SQL Server Integration Services 12.0**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="fe726-112">Sous l'onglet **Sécurité** , cliquez sur **Modifier** dans la zone **Autorisations d'exécution et d'activation** .</span><span class="sxs-lookup"><span data-stu-id="fe726-112">On the **Security** tab, click **Edit** in the **Launch and Activation Permissions** area.</span></span>  
  
5.  <span data-ttu-id="fe726-113">Ajoutez des utilisateurs et affectez les autorisations appropriées, puis cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="fe726-113">Add users and assign appropriate permissions, and then click Ok.</span></span>  
  
6.  <span data-ttu-id="fe726-114">Répétez les étapes 4 à 5 pour les autorisations d'accès.</span><span class="sxs-lookup"><span data-stu-id="fe726-114">Repeat steps 4 - 5 for Access Permissions.</span></span>  
  
7.  <span data-ttu-id="fe726-115">Redémarrez SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="fe726-115">Restart SQL Server Management Studio.</span></span>  
  
8.  <span data-ttu-id="fe726-116">Redémarrez le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fe726-116">Restart the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Service.</span></span>  
  
  
