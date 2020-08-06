---
title: Connecteur Microsoft 1,1 pour SAP BW | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5281f080-53d5-4679-aa26-f4cd4ac7a2df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ec5cfe83b201976be0512c54b77bc79f8aa824b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705271"
---
# <a name="microsoft-connector-11-for-sap-bw"></a><span data-ttu-id="d2e23-102">Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="d2e23-102">Microsoft Connector 1.1 for SAP BW</span></span>
  <span data-ttu-id="d2e23-103">[!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 pour SAP BW consiste en un jeu de trois composants qui vous permettent d'extraire ou de charger des données dans un système SAP Netweaver BW version 7.</span><span class="sxs-lookup"><span data-stu-id="d2e23-103">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW consists of a set of three components that let you extract data from, or load data into, an SAP Netweaver BW version 7 system.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d2e23-104">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="d2e23-104">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="d2e23-105">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="d2e23-105">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d2e23-106">Vous devez disposer d'une licence SAP supplémentaire pour extraire des données à partir de SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="d2e23-106">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="d2e23-107">Vérifiez auprès de SAP.</span><span class="sxs-lookup"><span data-stu-id="d2e23-107">Check with SAP to verify these requirements.</span></span>  
  
## <a name="components"></a><span data-ttu-id="d2e23-108">Components</span><span class="sxs-lookup"><span data-stu-id="d2e23-108">Components</span></span>  
 <span data-ttu-id="d2e23-109">[!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 pour SAP BW comprend les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="d2e23-109">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW has the following components:</span></span>  
  
-   <span data-ttu-id="d2e23-110">**Source SAP BW** : la source SAP BW est un composant source de flux de données qui vous permet d’extraire des données d’un système SAP Netweaver BW version 7.</span><span class="sxs-lookup"><span data-stu-id="d2e23-110">**SAP BW Source**-The SAP BW source is a data flow source component that lets you extract data from an SAP Netweaver BW version 7 system.</span></span>  
  
-   <span data-ttu-id="d2e23-111">**Destination SAP BW** : la destination SAP BW est un composant de destination de flux de données qui vous permet de charger des données dans un système SAP Netweaver BW version 7.</span><span class="sxs-lookup"><span data-stu-id="d2e23-111">**SAP BW Destination**-The SAP BW destination is a data flow destination component that lets you load data into an SAP Netweaver BW version 7 system.</span></span>  
  
-   <span data-ttu-id="d2e23-112">**Gestionnaire de connexions SAP BW** : le gestionnaire de connexions SAP BW connecte une source SAP BW ou une destination SAP BW à un système SAP Netweaver BW version 7.</span><span class="sxs-lookup"><span data-stu-id="d2e23-112">**SAP BW Connection Manager**-The SAP BW connection manager connects either an SAP BW source or SAP BW destination to an SAP Netweaver BW version 7 system.</span></span>  
  
 <span data-ttu-id="d2e23-113">Pour obtenir la procédure pas à pas qui montre comment configurer et utiliser le gestionnaire de connexions, la source et la destination SAP BW, consultez le livre blanc [Utilisation de SQL Server Integration Services avec SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkId=301897).</span><span class="sxs-lookup"><span data-stu-id="d2e23-113">For a walkthrough that demonstrates how to configure and use the SAP BW connection manager, source, and destination, see the white paper, [Using SQL Server Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkId=301897).</span></span> <span data-ttu-id="d2e23-114">Ce livre blanc explique également comment configurer les objets nécessaires dans SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d2e23-114">This white paper also shows how to configure the required objects in SAP BW.</span></span>  
  
## <a name="documentation"></a><span data-ttu-id="d2e23-115">Documentation</span><span class="sxs-lookup"><span data-stu-id="d2e23-115">Documentation</span></span>  
 <span data-ttu-id="d2e23-116">Ce fichier d'aide de [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 pour SAP BW contient les rubriques et les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="d2e23-116">This Help file for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW contains the following topics and sections:</span></span>  
  
 [<span data-ttu-id="d2e23-117">Installation de Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="d2e23-117">Installing the Microsoft Connector for 1.1 SAP BW</span></span>](installing-the-microsoft-connector-for-sap-bw.md)  
 <span data-ttu-id="d2e23-118">Décrit la configuration requise pour l'installation de [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 pour SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d2e23-118">Describes the installation requirements for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span>  
  
 [<span data-ttu-id="d2e23-119">Composants Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="d2e23-119">Microsoft Connector 1.1 for SAP BW Components</span></span>](microsoft-connector-for-sap-bw-components.md)  
 <span data-ttu-id="d2e23-120">Décrit chaque composant de [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 pour SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d2e23-120">Describes each component of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span>  
  
 [<span data-ttu-id="d2e23-121">Aide (F1) sur Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="d2e23-121">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](microsoft-connector-for-sap-bw-f1-help.md)  
 <span data-ttu-id="d2e23-122">Décrit l'interface utilisateur de chaque composant de [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 pour SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d2e23-122">Describes the user interface of each component of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span>  
  
  
