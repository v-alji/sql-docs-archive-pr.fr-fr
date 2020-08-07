---
title: Detail, propriété | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Detail property
- SoapException class
ms.assetid: c1ddaeb6-c540-49fa-b06e-b6359d377ee8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 060fbaba2b8d4f5a5171e8aa7995432622ba2ba0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703831"
---
# <a name="detail-property"></a><span data-ttu-id="2e604-102">Propriété Detail</span><span class="sxs-lookup"><span data-stu-id="2e604-102">Detail Property</span></span>
  <span data-ttu-id="2e604-103">La propriété **Detail** de la classe [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] **SoapException** possède la structure XML suivante :</span><span class="sxs-lookup"><span data-stu-id="2e604-103">The **Detail** property of the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] **SoapException** class has the following XML structure:</span></span>  
  
## <a name="elements"></a><span data-ttu-id="2e604-104">Éléments</span><span class="sxs-lookup"><span data-stu-id="2e604-104">Elements</span></span>  
 <span data-ttu-id="2e604-105">**Detail**</span><span class="sxs-lookup"><span data-stu-id="2e604-105">**Detail**</span></span>  
 <span data-ttu-id="2e604-106">Élément de niveau supérieur qui contient tous les autres éléments de détail de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="2e604-106">The top-level element that contains all other error detail elements.</span></span>  
  
 <span data-ttu-id="2e604-107">**ErrorCode**</span><span class="sxs-lookup"><span data-stu-id="2e604-107">**ErrorCode**</span></span>  
 <span data-ttu-id="2e604-108">Code d'erreur propre à [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e604-108">The [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-specific error code.</span></span>  
  
 <span data-ttu-id="2e604-109">**HttpStatus**</span><span class="sxs-lookup"><span data-stu-id="2e604-109">**HttpStatus**</span></span>  
 <span data-ttu-id="2e604-110">Code d'état HTTP.</span><span class="sxs-lookup"><span data-stu-id="2e604-110">The HTTP status code.</span></span>  
  
 <span data-ttu-id="2e604-111">**Message**</span><span class="sxs-lookup"><span data-stu-id="2e604-111">**Message**</span></span>  
 <span data-ttu-id="2e604-112">Message d'erreur et code d'erreur attribués par le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2e604-112">The error message and the error code assigned by the report server.</span></span>  
  
 <span data-ttu-id="2e604-113">**HelpLink**</span><span class="sxs-lookup"><span data-stu-id="2e604-113">**HelpLink**</span></span>  
 <span data-ttu-id="2e604-114">URL du lien d'aide vers un site Web sur lequel des informations complémentaires sur l'erreur sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="2e604-114">The Help link URL to a Web site at which further information about the error can be found.</span></span> <span data-ttu-id="2e604-115">Pour plus d’informations, consultez [HelpLink, élément](helplink-element.md).</span><span class="sxs-lookup"><span data-stu-id="2e604-115">For more information, see [HelpLink Element](helplink-element.md).</span></span>  
  
 <span data-ttu-id="2e604-116">**LinkID**</span><span class="sxs-lookup"><span data-stu-id="2e604-116">**LinkID**</span></span>  
 <span data-ttu-id="2e604-117">ID assigné au lien.</span><span class="sxs-lookup"><span data-stu-id="2e604-117">The ID assigned to the link.</span></span>  
  
 <span data-ttu-id="2e604-118">**ProductName**</span><span class="sxs-lookup"><span data-stu-id="2e604-118">**ProductName**</span></span>  
 <span data-ttu-id="2e604-119">Nom du produit.</span><span class="sxs-lookup"><span data-stu-id="2e604-119">The name of the product.</span></span> <span data-ttu-id="2e604-120">La valeur par défaut est **Microsoft SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="2e604-120">The default value is **Microsoft SQL Server Reporting Services**.</span></span>  
  
 <span data-ttu-id="2e604-121">**ProductVersion**</span><span class="sxs-lookup"><span data-stu-id="2e604-121">**ProductVersion**</span></span>  
 <span data-ttu-id="2e604-122">Version de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e604-122">The version of [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="2e604-123">La longueur maximale autorisée s'élève à 15 caractères.</span><span class="sxs-lookup"><span data-stu-id="2e604-123">The maximum length is 15 characters.</span></span> <span data-ttu-id="2e604-124">Le format du numéro de version doit être comme suit : 8.00.0xxx.00.</span><span class="sxs-lookup"><span data-stu-id="2e604-124">The format of the version number should be as follows: 8.00.0xxx.00.</span></span>  
  
 <span data-ttu-id="2e604-125">**ProductLocaleId**</span><span class="sxs-lookup"><span data-stu-id="2e604-125">**ProductLocaleId**</span></span>  
 <span data-ttu-id="2e604-126">ID des paramètres régionaux ou ID de la langue de la DLL INTL de l'application (par exemple, 0x41A).</span><span class="sxs-lookup"><span data-stu-id="2e604-126">The locale ID or language ID of the application's INTL DLL (for example, 0x41A).</span></span>  
  
 <span data-ttu-id="2e604-127">**Exploitation**</span><span class="sxs-lookup"><span data-stu-id="2e604-127">**OperatingSystem**</span></span>  
 <span data-ttu-id="2e604-128">Système d'exploitation sur lequel [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] est installé.</span><span class="sxs-lookup"><span data-stu-id="2e604-128">The operating system [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] is installed on.</span></span> <span data-ttu-id="2e604-129">Les valeurs valides incluent **0** pour un système d’exploitation indépendant, **1** pour [!INCLUDE[win2kfamily](../../../includes/win2kfamily-md.md)] et **16** pour Windows XP.</span><span class="sxs-lookup"><span data-stu-id="2e604-129">Valid values include **0** for operating system independent, **1** for [!INCLUDE[win2kfamily](../../../includes/win2kfamily-md.md)], and **16** for Windows XP.</span></span>  
  
 <span data-ttu-id="2e604-130">**CountryLocaleId**</span><span class="sxs-lookup"><span data-stu-id="2e604-130">**CountryLocaleId**</span></span>  
 <span data-ttu-id="2e604-131">ID des paramètres régionaux ou ID de la langue du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="2e604-131">The locale ID or language ID of the operating system.</span></span> <span data-ttu-id="2e604-132">Par exemple, la valeur de la version française de Windows est 0x040c.</span><span class="sxs-lookup"><span data-stu-id="2e604-132">For example, the value for the French version of Windows is 0x040c.</span></span>  
  
 <span data-ttu-id="2e604-133">**MoreInformation**</span><span class="sxs-lookup"><span data-stu-id="2e604-133">**MoreInformation**</span></span>  
 <span data-ttu-id="2e604-134">Chaîne XML qui contient des exceptions imbriquées qui se sont produites pendant l'exécution de la méthode.</span><span class="sxs-lookup"><span data-stu-id="2e604-134">An XML string that contains nested exceptions that occurred while the method ran.</span></span>  
  
 <span data-ttu-id="2e604-135">**Source**</span><span class="sxs-lookup"><span data-stu-id="2e604-135">**Source**</span></span>  
 <span data-ttu-id="2e604-136">Élément enfant de **MoreInformation**.</span><span class="sxs-lookup"><span data-stu-id="2e604-136">A child element of **MoreInformation**.</span></span> <span data-ttu-id="2e604-137">Source de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="2e604-137">The source of the error.</span></span>  
  
 <span data-ttu-id="2e604-138">**Message**</span><span class="sxs-lookup"><span data-stu-id="2e604-138">**Message**</span></span>  
 <span data-ttu-id="2e604-139">Élément enfant de **MoreInformation**.</span><span class="sxs-lookup"><span data-stu-id="2e604-139">A child element of **MoreInformation**.</span></span> <span data-ttu-id="2e604-140">Message d'erreur de l'exception imbriquée.</span><span class="sxs-lookup"><span data-stu-id="2e604-140">The error message of a nested exception.</span></span> <span data-ttu-id="2e604-141">Cet élément inclut des attributs XML pour **ErrorCode** et **HelpLink**.</span><span class="sxs-lookup"><span data-stu-id="2e604-141">This element includes XML attributes for **ErrorCode** and **HelpLink**.</span></span>  
  
 <span data-ttu-id="2e604-142">**Avertissements**</span><span class="sxs-lookup"><span data-stu-id="2e604-142">**Warnings**</span></span>  
 <span data-ttu-id="2e604-143">Chaîne XML qui contient les avertissements retournés par le traitement des rapports.</span><span class="sxs-lookup"><span data-stu-id="2e604-143">An XML string that contains the warnings returned from report processing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e604-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2e604-144">See Also</span></span>  
 <span data-ttu-id="2e604-145">[Présentation de la gestion des exceptions dans Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="2e604-145">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 <span data-ttu-id="2e604-146">[Reporting Services SoapException (classe)](reporting-services-soapexception-class.md) </span><span class="sxs-lookup"><span data-stu-id="2e604-146">[Reporting Services SoapException Class](reporting-services-soapexception-class.md) </span></span>  
 [<span data-ttu-id="2e604-147">Utilisation de la propriété Detail pour gérer des erreurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="2e604-147">Using the Detail Property to Handle Specific Errors</span></span>](../best-practices/using-the-detail-property-to-handle-specific-errors.md)  
  
  
