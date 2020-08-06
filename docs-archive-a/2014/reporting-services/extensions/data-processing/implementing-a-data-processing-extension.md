---
title: IMise en œuvre d’une extension pour le traitement des données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom data processing extensions [Reporting Services]
- data sources [Reporting Services], data processing extensions
- data processing extensions [Reporting Services]
- extensions [Reporting Services], data processing
ms.assetid: 8dc2b44e-5ad9-411d-a29f-7213e29321a9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5a1b7668f2319e742dcf3f1969fc3c5cc85cd7eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708951"
---
# <a name="implementing-a-data-processing-extension"></a><span data-ttu-id="32db3-102">Implémentation d'une extension pour le traitement des données</span><span class="sxs-lookup"><span data-stu-id="32db3-102">Implementing a Data Processing Extension</span></span>
  <span data-ttu-id="32db3-103">Les extensions pour le traitement des données dans [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] vous permettent de vous connecter à une source de données et de récupérer des données.</span><span class="sxs-lookup"><span data-stu-id="32db3-103">Data processing extensions in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] enable you to connect to a data source and retrieve data.</span></span> <span data-ttu-id="32db3-104">Elles servent également de pont entre une source de données et un dataset</span><span class="sxs-lookup"><span data-stu-id="32db3-104">They also serve as a bridge between a data source and a dataset.</span></span> <span data-ttu-id="32db3-105">Les extensions pour le traitement des données [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] sont basées sur un sous-ensemble des interfaces de fournisseur de données [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32db3-105">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extensions are modeled after a subset of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] data provider interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="32db3-106">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="32db3-106">In This Section</span></span>  
 [<span data-ttu-id="32db3-107">Vue d'ensemble des extensions pour le traitement des données</span><span class="sxs-lookup"><span data-stu-id="32db3-107">Data Processing Extensions Overview</span></span>](data-processing-extensions-overview.md)  
 <span data-ttu-id="32db3-108">Explique comment écrire une extension personnalisée pour le traitement des données pour [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32db3-108">Introduces how to write a custom data processing extension for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="32db3-109">Préparation de la mise en œuvre d'une classe de commande pour une extension</span><span class="sxs-lookup"><span data-stu-id="32db3-109">Preparing to Implement a Data Processing Extension</span></span>](preparing-to-implement-a-data-processing-extension.md)  
 <span data-ttu-id="32db3-110">Décrit les interfaces disponibles pour l'implémentation d'une extension pour le traitement des données [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], ainsi que l'implémentation d'une interface particulière.</span><span class="sxs-lookup"><span data-stu-id="32db3-110">Describes the interfaces available when implementing an [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension, as well as when you are required to implement a particular interface.</span></span>  
  
 [<span data-ttu-id="32db3-111">Création d'une bibliothèque d'extensions pour le traitement des données</span><span class="sxs-lookup"><span data-stu-id="32db3-111">Creating a Data Processing Extension Library</span></span>](creating-a-data-processing-extension-library.md)  
 <span data-ttu-id="32db3-112">Décrit l'assignation d'un espace de noms pour votre extension pour le traitement des données [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] et la compilation de votre extension pour le traitement des données dans une DLL de bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="32db3-112">Describes assigning a namespace for your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension and compiling your data processing extension into a library DLL.</span></span>  
  
 [<span data-ttu-id="32db3-113">Mise en œuvre d'une classe de connexion pour une extension pour le traitement des données</span><span class="sxs-lookup"><span data-stu-id="32db3-113">Implementing a Connection Class for a Data Processing Extension</span></span>](implementing-a-connection-class-for-a-data-processing-extension.md)  
 <span data-ttu-id="32db3-114">Décrit les attributs d’une connexion et comment implémenter votre propre classe **Connection** pour votre extension pour le traitement des données.</span><span class="sxs-lookup"><span data-stu-id="32db3-114">Describes the attributes of a connection and how to implement your own **Connection** class for your data processing extension.</span></span>  
  
 [<span data-ttu-id="32db3-115">Mise en œuvre d'une classe de commande pour une extension pour le traitement des données</span><span class="sxs-lookup"><span data-stu-id="32db3-115">Implementing a Command Class for a Data Processing Extension</span></span>](implementing-a-command-class-for-a-data-processing-extension.md)  
 <span data-ttu-id="32db3-116">Décrit les attributs d’une commande et comment implémenter votre propre classe **Command** pour votre extension pour le traitement des données.</span><span class="sxs-lookup"><span data-stu-id="32db3-116">Describes the attributes of a command, and how to implement your own **Command** class for your data processing extension.</span></span>  
  
 [<span data-ttu-id="32db3-117">Mise en œuvre d'une classe DataReader pour une extension pour le traitement des données</span><span class="sxs-lookup"><span data-stu-id="32db3-117">Implementing a DataReader Class for a Data Processing Extension</span></span>](implementing-a-datareader-class-for-a-data-processing-extension.md)  
 <span data-ttu-id="32db3-118">Décrit les attributs d’un lecteur de données et comment implémenter votre propre classe **DataReader** pour votre extension pour le traitement des données.</span><span class="sxs-lookup"><span data-stu-id="32db3-118">Describes the attributes of a data reader and how to implement your own **DataReader** class for your data processing extension.</span></span>  
  
 [<span data-ttu-id="32db3-119">Utilisation d'un jeu de données externe avec Reporting Services</span><span class="sxs-lookup"><span data-stu-id="32db3-119">Using an External Dataset with Reporting Services</span></span>](using-an-external-dataset-with-reporting-services.md)  
 <span data-ttu-id="32db3-120">Décrit comment exposer vos objets **DataSet** personnalisés sur le serveur de rapports pour être exploité.</span><span class="sxs-lookup"><span data-stu-id="32db3-120">Describes how to expose your custom **DataSet** objects to the report server for consumption.</span></span>  
  
 [<span data-ttu-id="32db3-121">Déploiement d'une extension pour le traitement des données</span><span class="sxs-lookup"><span data-stu-id="32db3-121">Deploying a Data Processing Extension</span></span>](deploying-a-data-processing-extension.md)  
 <span data-ttu-id="32db3-122">Décrit comment déployer votre extension pour le traitement des données.</span><span class="sxs-lookup"><span data-stu-id="32db3-122">Describes how to deploy your data processing extension.</span></span>  
  
 [<span data-ttu-id="32db3-123">Débogage du code des extensions pour le traitement des données</span><span class="sxs-lookup"><span data-stu-id="32db3-123">Debugging Data Processing Extension Code</span></span>](debugging-data-processing-extension-code.md)  
 <span data-ttu-id="32db3-124">Décrit comment déboguer le code dans vos extensions pour le traitement des données.</span><span class="sxs-lookup"><span data-stu-id="32db3-124">Describes how to debug code in your data processing extensions.</span></span>  
  
 [<span data-ttu-id="32db3-125">Suppression d'une extension pour le traitement des données</span><span class="sxs-lookup"><span data-stu-id="32db3-125">Removing a Data Processing Extension</span></span>](removing-a-data-processing-extension.md)  
 <span data-ttu-id="32db3-126">Décrit comment supprimer une extension pour le traitement des données d'un serveur de rapports ou d'un Concepteur de rapports.</span><span class="sxs-lookup"><span data-stu-id="32db3-126">Describes how to remove a data processing extension from a report server or Report Designer.</span></span>  
  
 <span data-ttu-id="32db3-127">Pour un exemple d’extension pour le traitement des données totalement implémentée, consultez [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889) (Exemples Reporting Services pour le produit SQL Server).</span><span class="sxs-lookup"><span data-stu-id="32db3-127">For a sample of a fully implemented data processing extension, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32db3-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="32db3-128">See Also</span></span>  
 <span data-ttu-id="32db3-129">[Extensions de Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="32db3-129">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="32db3-130">Bibliothèque d'extensions Reporting Services</span><span class="sxs-lookup"><span data-stu-id="32db3-130">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
