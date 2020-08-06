---
title: Installation du connecteur Microsoft pour 1,1 SAP BW | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3bfb9023-9597-4f59-9085-4b9057e7702e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0ef96f38054f04e71de72bda0bbb12f8f003ef20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604634"
---
# <a name="installing-the-microsoft-connector-for-11-sap-bw"></a><span data-ttu-id="f477c-102">Installation de Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="f477c-102">Installing the Microsoft Connector for 1.1 SAP BW</span></span>
  <span data-ttu-id="f477c-103">Pour installer le [!INCLUDE[msCoName](../includes/msconame-md.md)] connecteur 1,1 pour SAP BW et sa documentation, téléchargez et exécutez le package Windows Installer à partir de la page Web du Feature Pack SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f477c-103">To install the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW and its documentation, download and run the Windows installer package from the SQL Server Feature Pack Web page.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f477c-104">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="f477c-104">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="f477c-105">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="f477c-105">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f477c-106">Vous devez disposer d'une licence SAP supplémentaire pour extraire des données à partir de SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="f477c-106">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="f477c-107">Vérifiez auprès de SAP.</span><span class="sxs-lookup"><span data-stu-id="f477c-107">Check with SAP to verify these requirements.</span></span>  
  
## <a name="required-sap-files"></a><span data-ttu-id="f477c-108">Fichiers SAP requis</span><span class="sxs-lookup"><span data-stu-id="f477c-108">Required SAP Files</span></span>  
 <span data-ttu-id="f477c-109">Pour utiliser le [!INCLUDE[msCoName](../includes/msconame-md.md)] connecteur 1,1 pour SAP BW, il n’est pas nécessaire d’installer le logiciel frontal SAP (GUI SAP) sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="f477c-109">To use the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW, you do not have to install the SAP Front End software (SAP GUI) on the local computer.</span></span>  
  
 <span data-ttu-id="f477c-110">Cependant, vous devez copier le fichier du connecteur SAP .NET, librfc32.dll, dans le sous-dossier système du dossier Windows.</span><span class="sxs-lookup"><span data-stu-id="f477c-110">However you must copy the SAP .NET connector file, librfc32.dll, into the system subfolder in the Windows folder.</span></span> <span data-ttu-id="f477c-111">(En général, l’emplacement de ce dossier est **C:\Windows\system32**.)</span><span class="sxs-lookup"><span data-stu-id="f477c-111">(Typically, this folder location is **C:\Windows\system32**.)</span></span>  
  
## <a name="considerations-for-64-bit-computers"></a><span data-ttu-id="f477c-112">Éléments à prendre en considération pour les ordinateurs 64 bits</span><span class="sxs-lookup"><span data-stu-id="f477c-112">Considerations for 64-bit Computers</span></span>  
 <span data-ttu-id="f477c-113">Le [!INCLUDE[msCoName](../includes/msconame-md.md)] connecteur 1,1 pour SAP BW prend entièrement en charge la version 64 bits de [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="f477c-113">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW fully supports the 64-bit version of [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span></span> <span data-ttu-id="f477c-114">Sur un ordinateur 64 bits, le [!INCLUDE[msCoName](../includes/msconame-md.md)] connecteur 1,1 pour SAP BW présente les conditions supplémentaires suivantes :</span><span class="sxs-lookup"><span data-stu-id="f477c-114">On a 64-bit computer, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW has the following additional requirements:</span></span>  
  
-   <span data-ttu-id="f477c-115">Pour exécuter les packages en mode 64 bits sur les systèmes d’exploitation Windows 64 bits, copiez la version 64 bits du fichier d’interface GUI SAP, librfc32.dll, dans le dossier **system32** du dossier Windows.</span><span class="sxs-lookup"><span data-stu-id="f477c-115">To run packages in 64-bit mode on any 64-bit Windows operating system, copy the 64-bit version of the SAP GUI file, librfc32.dll, into the **system32** folder of the Windows folder.</span></span> <span data-ttu-id="f477c-116">(En général, l’emplacement de ce fichier est **C:\Windows\system32**.)</span><span class="sxs-lookup"><span data-stu-id="f477c-116">(Typically, this file location is **C:\Windows\system32**.)</span></span>  
  
-   <span data-ttu-id="f477c-117">Pour exécuter les packages en mode 32 bits sur les systèmes d’exploitation Windows 64 bits, copiez le fichier d’interface GUI SAP, librfc32.dll, dans le dossier **SysWow64** du dossier Windows.</span><span class="sxs-lookup"><span data-stu-id="f477c-117">To run packages in 32-bit mode on any 64-bit Windows operating system, copy the SAP GUI file, librfc32.dll, into the **SysWow64** folder of the Windows folder.</span></span> <span data-ttu-id="f477c-118">(En général, l’emplacement de ce dossier est **C:\Windows\SysWow64**.)</span><span class="sxs-lookup"><span data-stu-id="f477c-118">(Typically, this folder location is **C:\Windows\SysWow64**.)</span></span>  
  
  
