---
title: Méthodes d’autorisation | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], reports
- authorization [Reporting Services]
- reports [Reporting Services], security
- tasks [Reporting Services]
- roles [Reporting Services], methods
ms.assetid: 45e9cf2c-facf-4801-9482-c855403f42a8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b04a21b5075e939a4732e2f8ec219e169f4ba440
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704875"
---
# <a name="authorization-methods"></a><span data-ttu-id="e6674-102">Méthodes d'autorisation</span><span class="sxs-lookup"><span data-stu-id="e6674-102">Authorization Methods</span></span>
  <span data-ttu-id="e6674-103">Vous pouvez utiliser les méthodes suivantes pour gérer les tâches, les rôles et les stratégies sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="e6674-103">You can use these methods to manage tasks, roles, and policies on the report server.</span></span>  
  
|<span data-ttu-id="e6674-104">Méthode</span><span class="sxs-lookup"><span data-stu-id="e6674-104">Method</span></span>|<span data-ttu-id="e6674-105">Action</span><span class="sxs-lookup"><span data-stu-id="e6674-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.CreateRole%2A>|<span data-ttu-id="e6674-106">Ajoute un nouveau rôle à la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="e6674-106">Adds a new role to the report server database.</span></span> <span data-ttu-id="e6674-107">Cette méthode s’applique uniquement au mode natif.</span><span class="sxs-lookup"><span data-stu-id="e6674-107">This method =applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DeleteRole%2A>|<span data-ttu-id="e6674-108">Supprime un rôle de la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="e6674-108">Deletes a role from the report server database.</span></span> <span data-ttu-id="e6674-109">Cette méthode s’applique uniquement au mode natif.</span><span class="sxs-lookup"><span data-stu-id="e6674-109">This method applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetPermissions%2A>|<span data-ttu-id="e6674-110">Retourne les autorisations utilisateur associées à un élément particulier de la base de données du serveur de rapports ou la bibliothèque SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e6674-110">Returns the user permissions that are associated with a particular item in the report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetPolicies%2A>|<span data-ttu-id="e6674-111">Retourne les stratégies associées à un élément particulier de la base de données du serveur de rapports ou la bibliothèque SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e6674-111">Returns the policies that are associated with a particular item in the report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetRoleProperties%2A>|<span data-ttu-id="e6674-112">Retourne les propriétés de métadonnées de rôle et une collection de tâches associées.</span><span class="sxs-lookup"><span data-stu-id="e6674-112">Returns role metadata properties and a collection of associated tasks.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetSystemPermissions%2A>|<span data-ttu-id="e6674-113">Retourne les autorisations système de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e6674-113">Returns the user's system permissions.</span></span> <span data-ttu-id="e6674-114">Cette méthode s’applique uniquement au mode natif.</span><span class="sxs-lookup"><span data-stu-id="e6674-114">This method applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetSystemPolicies%2A>|<span data-ttu-id="e6674-115">Retourne les stratégies système, y compris les groupes et les rôles auxquels elles sont associées.</span><span class="sxs-lookup"><span data-stu-id="e6674-115">Returns the system policies, including groups and roles with which they are associated.</span></span> <span data-ttu-id="e6674-116">Cette méthode s’applique uniquement au mode natif.</span><span class="sxs-lookup"><span data-stu-id="e6674-116">This method applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.InheritParentSecurity%2A>|<span data-ttu-id="e6674-117">Supprime les stratégies qui sont associées à un élément particulier de la base de données du serveur de rapports et définit les stratégies de sécurité de l’élément sur celles de son parent.</span><span class="sxs-lookup"><span data-stu-id="e6674-117">Deletes the policies that are associated with a particular item in the report server database and sets the security policies for the item to those of its parent.</span></span>|  
|<xref:ReportService2010.ReportingService2010.IsSSLRequired%2A>|<span data-ttu-id="e6674-118">Renvoie une valeur booléenne qui indique si le protocole Secure Socket Layer (SSL) est obligatoire pour utiliser le point de terminaison <xref:ReportService2010>.</span><span class="sxs-lookup"><span data-stu-id="e6674-118">Returns a Boolean value that indicates whether the Secure Socket Layer (SSL) protocol is required to use the <xref:ReportService2010> end point.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListRoles%2A>|<span data-ttu-id="e6674-119">Retourne les noms et descriptions des rôles gérés par le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="e6674-119">Returns the names and descriptions of roles that are managed by the report server.</span></span>|  
|<xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A>|<span data-ttu-id="e6674-120">Retourne la liste des méthodes SOAP (Simple Object Access Protocol) dans le point de terminaison <xref:ReportExecution2005>qui requièrent une connexion sécurisée lorsqu'elles sont appelées.</span><span class="sxs-lookup"><span data-stu-id="e6674-120">Returns a list of Simple Object Access Protocol (SOAP) methods in the <xref:ReportExecution2005> endpoint that require a secure connection when invoked.</span></span> <span data-ttu-id="e6674-121">Le paramètre `SecureConnectionLevel` du serveur de rapports est utilisé pour déterminer quelles méthodes sont retournées.</span><span class="sxs-lookup"><span data-stu-id="e6674-121">The `SecureConnectionLevel` setting of the report server is used to determine which methods are returned.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListTasks%2A>|<span data-ttu-id="e6674-122">Retourne les tâches gérées par le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="e6674-122">Returns the tasks that are managed by the report server.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetPolicies%2A>|<span data-ttu-id="e6674-123">Définit les stratégies associées à un élément spécifié.</span><span class="sxs-lookup"><span data-stu-id="e6674-123">Sets the policies that are associated with a specified item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetRoleProperties%2A>|<span data-ttu-id="e6674-124">Définit les propriétés de métadonnées de rôle et associe un jeu de tâches à un rôle.</span><span class="sxs-lookup"><span data-stu-id="e6674-124">Sets role metadata properties and associates a set of tasks with a role.</span></span> <span data-ttu-id="e6674-125">Cette méthode s’applique uniquement au mode natif.</span><span class="sxs-lookup"><span data-stu-id="e6674-125">This method applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetSystemPolicies%2A>|<span data-ttu-id="e6674-126">Définit la stratégie système qui définit des groupes et leurs rôles associés.</span><span class="sxs-lookup"><span data-stu-id="e6674-126">Sets the system policy that defines groups and their associated roles.</span></span> <span data-ttu-id="e6674-127">Cette méthode s’applique uniquement au mode natif.</span><span class="sxs-lookup"><span data-stu-id="e6674-127">This method applies to native mode only.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e6674-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e6674-128">See Also</span></span>  
 <span data-ttu-id="e6674-129">[Création d’applications à l’aide du service web et du .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="e6674-129">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="e6674-130">[Service web Report Server](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="e6674-130">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="e6674-131">[Méthodes du service web Report Server](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="e6674-131">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="e6674-132">Informations techniques de référence &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e6674-132">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
