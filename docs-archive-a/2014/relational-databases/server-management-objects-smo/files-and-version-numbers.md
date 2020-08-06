---
title: Fichiers et numéros de version | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Management Objects, versions
- components [SMO]
- files [SMO], components
- SMO [SQL Server], versions
- versions [SMO]
ms.assetid: 510907b6-e7a9-41bd-b892-d6d99a5118e1
author: stevestein
ms.author: sstein
ms.openlocfilehash: f1a7286f15af28f97e488b8b40fd745a0d320108
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605360"
---
# <a name="files-and-version-numbers"></a><span data-ttu-id="90268-102">Fichiers et numéros de version</span><span class="sxs-lookup"><span data-stu-id="90268-102">Files and Version Numbers</span></span>
  <span data-ttu-id="90268-103">Tous les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] composants Smo (Management Objects) requis sont installés dans le cadre d’une instance de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client ou serveur.</span><span class="sxs-lookup"><span data-stu-id="90268-103">All required [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO) components are installed as part of an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client or server.</span></span> <span data-ttu-id="90268-104">SMO est implémenté dans plusieurs assemblys managés.</span><span class="sxs-lookup"><span data-stu-id="90268-104">SMO is implemented in several managed assemblies.</span></span> <span data-ttu-id="90268-105">Vous pouvez développer des applications SMO sur un client ou sur un serveur.</span><span class="sxs-lookup"><span data-stu-id="90268-105">You can develop SMO applications on either a client or a server.</span></span>  
  
|<span data-ttu-id="90268-106">Répertoire</span><span class="sxs-lookup"><span data-stu-id="90268-106">Directory</span></span>|<span data-ttu-id="90268-107">Fichier</span><span class="sxs-lookup"><span data-stu-id="90268-107">File</span></span>|<span data-ttu-id="90268-108">Description</span><span class="sxs-lookup"><span data-stu-id="90268-108">Description</span></span>|  
|---------------|----------|-----------------|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="90268-109">Microsoft.SqlServer.ConnectionInfo.dll</span><span class="sxs-lookup"><span data-stu-id="90268-109">Microsoft.SqlServer.ConnectionInfo.dll</span></span>|<span data-ttu-id="90268-110">Assure la prise en charge de la connexion à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90268-110">Contains support for connecting to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="90268-111">Microsoft.SqlServer.ServiceBrokerEnum.dll</span><span class="sxs-lookup"><span data-stu-id="90268-111">Microsoft.SqlServer.ServiceBrokerEnum.dll</span></span>|<span data-ttu-id="90268-112">Assure la prise en charge de la programmation de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service Broker.</span><span class="sxs-lookup"><span data-stu-id="90268-112">Contains support for programming the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service Broker.</span></span> <span data-ttu-id="90268-113">Celle-ci n'est requise que dans les programmes qui accèdent au Service Broker.</span><span class="sxs-lookup"><span data-stu-id="90268-113">This is required only in programs that access the Service Broker.</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="90268-114">Microsoft.SqlServer.Smo.dll</span><span class="sxs-lookup"><span data-stu-id="90268-114">Microsoft.SqlServer.Smo.dll</span></span>|<span data-ttu-id="90268-115">Contient la plupart des classes SMO.</span><span class="sxs-lookup"><span data-stu-id="90268-115">Contains the most of the SMO classes.</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="90268-116">Microsoft.SqlServer.SmoExtended.dll</span><span class="sxs-lookup"><span data-stu-id="90268-116">Microsoft.SqlServer.SmoExtended.dll</span></span><br /><br /> <span data-ttu-id="90268-117">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span><span class="sxs-lookup"><span data-stu-id="90268-117">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span></span><br /><br /> <span data-ttu-id="90268-118">Microsoft.SqlServer.SqlEnum.dll</span><span class="sxs-lookup"><span data-stu-id="90268-118">Microsoft.SqlServer.SqlEnum.dll</span></span>|<span data-ttu-id="90268-119">Assure la prise en charge des classes SMO.</span><span class="sxs-lookup"><span data-stu-id="90268-119">Contains support for the SMO classes.</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="90268-120">Microsoft.SqlServer.WmiEnum.dll</span><span class="sxs-lookup"><span data-stu-id="90268-120">Microsoft.SqlServer.WmiEnum.dll</span></span>|<span data-ttu-id="90268-121">Contient les classes du fournisseur WMI (Windows Management Instrumentation).</span><span class="sxs-lookup"><span data-stu-id="90268-121">Contains the Windows Management Instrumentation (WMI) Provider classes.</span></span> <span data-ttu-id="90268-122">Celles-ci sont uniquement requises pour les programmes qui utilisent les classes du fournisseur WMI.</span><span class="sxs-lookup"><span data-stu-id="90268-122">This is required only for programs that use the WMI Provider classes.</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="90268-123">Microsoft.SqlServer.RegSvrEnum.dll</span><span class="sxs-lookup"><span data-stu-id="90268-123">Microsoft.SqlServer.RegSvrEnum.dll</span></span>|<span data-ttu-id="90268-124">Contient les classes de serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="90268-124">Contains the Registered Server classes.</span></span> <span data-ttu-id="90268-125">Celles-ci sont uniquement requises pour les programmes qui utilisent les classes de serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="90268-125">This is required only for programs that use the Registered Server classes.</span></span>|  
  
  
