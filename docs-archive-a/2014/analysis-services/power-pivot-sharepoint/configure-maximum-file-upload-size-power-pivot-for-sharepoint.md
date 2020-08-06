---
title: Configurer la taille maximale de téléchargement de fichiers (PowerPivot pour SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ac516c63-1e79-4ae8-bca6-32d3c1a09c00
author: minewiskan
ms.author: owend
ms.openlocfilehash: 34a0adb2f22915289cccfa1f21c51038263acca0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694739"
---
# <a name="configure-maximum-file-upload-size-powerpivot-for-sharepoint"></a><span data-ttu-id="97a50-102">Configurer la taille maximale de téléchargement de fichiers (PowerPivot pour SharePoint)</span><span class="sxs-lookup"><span data-stu-id="97a50-102">Configure Maximum File Upload Size (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="97a50-103">Les classeurs PowerPivot contiennent souvent des quantités importantes de données qui se traduisent par des fichiers dépassant la taille de fichier maximale autorisée pour les téléchargements SharePoint.</span><span class="sxs-lookup"><span data-stu-id="97a50-103">PowerPivot workbooks often contain large amounts of data that result in files that exceed the maximum file size allowed for SharePoint uploads.</span></span> <span data-ttu-id="97a50-104">Lorsque vous essayez de télécharger un fichier qui dépasse la limite supérieure, l'erreur suivante s'affiche dans SharePoint :</span><span class="sxs-lookup"><span data-stu-id="97a50-104">When you try to upload a file that exceeds the upper limit, you will get the following error on SharePoint:</span></span>  
  
-   <span data-ttu-id="97a50-105">« La taille du fichier spécifié est supérieure à la taille maximale de fichier prise en charge. »</span><span class="sxs-lookup"><span data-stu-id="97a50-105">"The specified file is larger than the maximum supported file size."</span></span>  
  
 <span data-ttu-id="97a50-106">Pour augmenter la taille de fichier, commencez par ajuster la valeur de l'option Taille maximale du classeur pour Excel Services à 50 mégaoctets.</span><span class="sxs-lookup"><span data-stu-id="97a50-106">To increase the file size, start by adjusting the Maximum Workbook Size for Excel Services to 50 megabytes.</span></span> <span data-ttu-id="97a50-107">Cela aligne les limites de taille de fichier maximale pour Excel sur celles des applications Web SharePoint (définies par défaut sur 50 mégaoctets dans SharePoint 2010, et sur 200 dans SharePoint 2013).</span><span class="sxs-lookup"><span data-stu-id="97a50-107">This aligns the maximum file size limits for Excel to those of SharePoint web applications (set to 50 megabytes by default in SharePoint 2010 and 200 in SharePoint 2013).</span></span> <span data-ttu-id="97a50-108">Si la taille de vos fichiers est supérieure à 50 mégaoctets, augmentez les limites de taille de fichier pour Excel Services ainsi que pour votre application Web.</span><span class="sxs-lookup"><span data-stu-id="97a50-108">If your files exceed 50 megabytes in size, increase the file size limits for both Excel Services and your web application.</span></span>  
  
 <span data-ttu-id="97a50-109">Vous devez être administrateur SharePoint pour modifier la taille maximale du téléchargement de fichiers.</span><span class="sxs-lookup"><span data-stu-id="97a50-109">You must be a SharePoint administrator to change the maximum file upload size.</span></span>  
  
### <a name="configure-maximum-file-size-for-excel-services"></a><span data-ttu-id="97a50-110">Configurer la taille de fichier maximale pour Excel Services</span><span class="sxs-lookup"><span data-stu-id="97a50-110">Configure maximum file size for Excel Services</span></span>  
  
1.  <span data-ttu-id="97a50-111">Dans l'Administration centrale, sous Gestion des applications, cliquez sur **Gérer les applications de service**.</span><span class="sxs-lookup"><span data-stu-id="97a50-111">In Central Administration, in Application Management, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="97a50-112">Cliquez sur le nom de votre application Excel Services.</span><span class="sxs-lookup"><span data-stu-id="97a50-112">Click the name of your Excel Services Application.</span></span>  
  
3.  <span data-ttu-id="97a50-113">Cliquez sur **Emplacements de fichiers approuvés**.</span><span class="sxs-lookup"><span data-stu-id="97a50-113">Click **Trusted File Locations**.</span></span>  
  
4.  <span data-ttu-id="97a50-114">Cliquez sur l'emplacement pour modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="97a50-114">Click the location to edit the properties.</span></span> <span data-ttu-id="97a50-115">Par défaut, Excel Services considère l'application Web par défaut comme un site de confiance.</span><span class="sxs-lookup"><span data-stu-id="97a50-115">By default, Excel Services considers the default web application a trusted site.</span></span> <span data-ttu-id="97a50-116">Si vous utilisez l’application web par défaut, cliquez sur **http://** pour ouvrir la page de configuration de cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="97a50-116">If you are using the default web application, click **http://** to open the configuration page for this location.</span></span>  
  
5.  <span data-ttu-id="97a50-117">Faites défiler la liste jusqu’à **Propriétés du classeur**.</span><span class="sxs-lookup"><span data-stu-id="97a50-117">Scroll to **Workbook Properties**.</span></span>  
  
6.  <span data-ttu-id="97a50-118">Dans Taille maximale du classeur, faites passer la taille de fichier de 10 (valeur par défaut) à 50 ou à une taille plus importante adaptée aux fichiers que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="97a50-118">In Maximum Workbook Size, increase the file size from 10 (the default value) to 50 or a larger size that accommodates the files you are working with.</span></span>  
  
     <span data-ttu-id="97a50-119">Par défaut, la taille maximale du téléchargement de fichiers pour les applications Web SharePoint est de 50 mégaoctets.</span><span class="sxs-lookup"><span data-stu-id="97a50-119">By default, 50 megabytes is the maximum file upload size for SharePoint web applications.</span></span> <span data-ttu-id="97a50-120">Si vous affectez à l'option Taille maximale du classeur une valeur supérieure à 50 mégaoctets, suivez les étapes de la procédure suivante pour affecter la même valeur à l'option Taille maximale du téléchargement pour votre application Web SharePoint.</span><span class="sxs-lookup"><span data-stu-id="97a50-120">If you set Maximum Workbook Size to a number larger than 50 megabytes, follow the steps in the next procedure to increase the Maximum Upload Size for your SharePoint web application to the same value.</span></span>  
  
     <span data-ttu-id="97a50-121">La valeur maximale que vous pouvez spécifier est 2 gigaoctets (ou 2 047 mégaoctets tel que le spécifie l'Administration centrale).</span><span class="sxs-lookup"><span data-stu-id="97a50-121">The maximum value that you can specify is 2 gigabytes (or 2047 megabytes as specified in Central Administration).</span></span>  
  
7.  <span data-ttu-id="97a50-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="97a50-122">Click **OK**.</span></span>  
  
### <a name="configure-maximum-file-size-for-a-sharepoint-web-application"></a><span data-ttu-id="97a50-123">Configurer la taille de fichier maximale pour une application Web SharePoint</span><span class="sxs-lookup"><span data-stu-id="97a50-123">Configure maximum file size for a SharePoint web application</span></span>  
  
1.  <span data-ttu-id="97a50-124">Dans administration centrale, dans gestion des applications, cliquez sur **gérer les applications Web**.</span><span class="sxs-lookup"><span data-stu-id="97a50-124">In Central Administration, in Application Management, click **Manage web applications**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="97a50-125">Effectuez les étapes suivantes uniquement si vous augmentez la Taille maximale du classeur dans Excel Services.</span><span class="sxs-lookup"><span data-stu-id="97a50-125">Perform the following steps only if you increased the Maximum Workbook Size in Excel Services.</span></span>  
  
2.  <span data-ttu-id="97a50-126">Sélectionnez l’application (par exemple, **SharePoint - 80**).</span><span class="sxs-lookup"><span data-stu-id="97a50-126">Select the application (for example, **SharePoint - 80**).</span></span>  
  
3.  <span data-ttu-id="97a50-127">Dans le ruban Applications Web, cliquez sur la flèche bas située sur le bouton Paramètres généraux.</span><span class="sxs-lookup"><span data-stu-id="97a50-127">On the Web Applications ribbon, click the down arrow on the General Settings button.</span></span>  
  
4.  <span data-ttu-id="97a50-128">Cliquez sur **Paramètres généraux**.</span><span class="sxs-lookup"><span data-stu-id="97a50-128">Click **General Settings**.</span></span>  
  
5.  <span data-ttu-id="97a50-129">Faites défiler la liste jusqu’à **Taille maximale du téléchargement**.</span><span class="sxs-lookup"><span data-stu-id="97a50-129">Scroll to **Maximum Upload Size**.</span></span>  
  
6.  <span data-ttu-id="97a50-130">Affectez à la propriété la même taille, ou une taille supérieure à la Taille maximale du classeur dans Excel Services.</span><span class="sxs-lookup"><span data-stu-id="97a50-130">Set the property to the same number, or larger as the Maximum Workbook Size in Excel Services.</span></span>  
  
7.  <span data-ttu-id="97a50-131">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="97a50-131">Click **OK**.</span></span>  
  
  
