---
title: Suppression d’une extension pour le traitement des données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- deleting data processing extensions
- data processing extensions [Reporting Services], removing
- removing data processing extensions
ms.assetid: 1d89e32b-0631-44f6-8178-a57fb791d26d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9f5dfd3a6a7615fa3fd91c917bba6dbf0808f0f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708944"
---
# <a name="removing-a-data-processing-extension"></a><span data-ttu-id="b8fbd-102">Suppression d'une extension pour le traitement des données</span><span class="sxs-lookup"><span data-stu-id="b8fbd-102">Removing a Data Processing Extension</span></span>
  <span data-ttu-id="b8fbd-103">Pour supprimer une extension pour le traitement des données, supprimez simplement l’élément **Extension** de votre extension pour le traitement des données du fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="b8fbd-103">To remove a data processing extension, simply remove the **Extension** element for your data processing extension from the configuration file.</span></span> <span data-ttu-id="b8fbd-104">Si vous avez créé des entrées pour un serveur de rapports et le Concepteur de rapports, supprimez l’élément **Extension** des fichiers RSReportServer.config et RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="b8fbd-104">If you made entries for a report server as well as Report Designer, remove the **Extension** element from both the RSReportServer.config and RSReportDesigner.config files.</span></span> <span data-ttu-id="b8fbd-105">Une fois les informations de configuration supprimées, l'extension pour le traitement des données n'est plus accessible au composant.</span><span class="sxs-lookup"><span data-stu-id="b8fbd-105">After the configuration information is removed, the data processing extension is no longer available to the component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8fbd-106">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b8fbd-106">See Also</span></span>  
 <span data-ttu-id="b8fbd-107">[Extensions de Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="b8fbd-107">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="b8fbd-108">[Implémentation d’une extension pour le traitement des données](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="b8fbd-108">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="b8fbd-109">Bibliothèque d'extensions Reporting Services</span><span class="sxs-lookup"><span data-stu-id="b8fbd-109">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
