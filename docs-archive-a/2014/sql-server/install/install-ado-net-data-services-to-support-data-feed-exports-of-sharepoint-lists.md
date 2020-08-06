---
title: Installer ADO.NET Data Services pour prendre en charge les exportations de flux de données des listes SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: f32527ae-f623-4e08-adfb-6d3262f5c2ac
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: fb47804daee38427f48baefdf3997edda5fb90b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603221"
---
# <a name="install-adonet-data-services-to-support-data-feed-exports-of-sharepoint-lists"></a><span data-ttu-id="11e64-102">Installation d'ADO.NET Data Services pour prendre en charge les exportations de flux de données des listes SharePoint</span><span class="sxs-lookup"><span data-stu-id="11e64-102">Install ADO.NET Data Services to support data feed exports of SharePoint lists</span></span>
  <span data-ttu-id="11e64-103">ADO.NET Data Services est requis pour une exportation de flux de données de listes SharePoint.</span><span class="sxs-lookup"><span data-stu-id="11e64-103">ADO.NET Data Services is required for a data feed export of SharePoint lists.</span></span> <span data-ttu-id="11e64-104">SharePoint 2010 n'inclut pas ce composant dans le programme d'installation des composants requis pour SharePoint. Par conséquent, vous devez l'installer manuellement.</span><span class="sxs-lookup"><span data-stu-id="11e64-104">SharePoint 2010 does not include this component in the SharePoint Prerequisite Installer program, so you must install it manually.</span></span>  
  
 <span data-ttu-id="11e64-105">Sans ce composant requis, vous obtenez l'erreur suivante lorsque vous essayez d'utiliser une liste SharePoint exportée en tant que flux de données : « pour des raisons de sécurité, la DTD est interdite dans ce document XML.</span><span class="sxs-lookup"><span data-stu-id="11e64-105">Without this prerequisite, you will get the following error when you attempt to use a SharePoint list that was exported as a data feed: "For security reasons DTD is prohibited in this XML document.</span></span> <span data-ttu-id="11e64-106">Pour activer le traitement DTD, affectez à la propriété ProhibitDtd de XmlReaderSettings la valeur False et transmettez les paramètres à la méthode XmlReader.Create ».</span><span class="sxs-lookup"><span data-stu-id="11e64-106">To enable DTD processing set the ProhibitDtd property on XmlReaderSettings to false and pass the settings into XmlReader.Create method."</span></span>  
  
 <span data-ttu-id="11e64-107">Utilisez les instructions suivantes pour installer ADO.NET Data Services sur chaque serveur SharePoint pour lequel vous voulez autoriser l'exportation de listes en tant que flux de données.</span><span class="sxs-lookup"><span data-stu-id="11e64-107">Use the following instructions to install ADO.NET Data Services on every SharePoint server for which you want to allow lists to be exported as data feeds.</span></span>  
  
### <a name="download-and-install-adonet-data-services"></a><span data-ttu-id="11e64-108">Télécharger et installer ADO.NET Data Services</span><span class="sxs-lookup"><span data-stu-id="11e64-108">Download and install ADO.NET Data Services</span></span>  
  
1.  <span data-ttu-id="11e64-109">Accédez à la documentation relative à la configuration matérielle et logicielle requise pour SharePoint 2010, [Configuration matérielle et logicielle requise (SharePoint 2010)](https://go.microsoft.com/fwlink/?LinkId=169734)</span><span class="sxs-lookup"><span data-stu-id="11e64-109">Go to the hardware and software requirements documentation for SharePoint 2010, [Hardware and Software Requirements (SharePoint 2010)](https://go.microsoft.com/fwlink/?LinkId=169734)</span></span>  
  
2.  <span data-ttu-id="11e64-110">Dans **accès aux logiciels applicables**, recherchez le lien pour ADO.NET Data Services 3,5 qui correspond au système d’exploitation que vous utilisez (windows Server 2008 SP2 ou windows Server 2008 R2).</span><span class="sxs-lookup"><span data-stu-id="11e64-110">In **Access to applicable software**, find the link for ADO.NET Data Services 3.5 that corresponds to the operating system you are using (either Windows Server 2008 SP2 or Windows Server 2008 R2).</span></span>  
  
3.  <span data-ttu-id="11e64-111">Cliquez sur le lien, puis exécutez le programme d'installation qui installe le service.</span><span class="sxs-lookup"><span data-stu-id="11e64-111">Click the link and run the setup program that installs the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11e64-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="11e64-112">See Also</span></span>  
 [<span data-ttu-id="11e64-113">PowerPivot for SharePoint 2010 Installation</span><span class="sxs-lookup"><span data-stu-id="11e64-113">PowerPivot for SharePoint 2010 Installation</span></span>](../../../2014/sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
  
  
