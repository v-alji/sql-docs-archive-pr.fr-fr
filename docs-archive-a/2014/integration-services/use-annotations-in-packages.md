---
title: Utiliser des annotations dans les packages | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- self-documenting packages
- adding annotations
- annotations [Integration Services]
ms.assetid: 48c8ed9a-b10d-490c-9ba7-4b77aa44e3dd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 27c7df6afd894ea9730027da1d54786ed8397fad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615201"
---
# <a name="use-annotations-in-packages"></a><span data-ttu-id="cd505-102">Utiliser des annotations dans les packages</span><span class="sxs-lookup"><span data-stu-id="cd505-102">Use Annotations in Packages</span></span>
  <span data-ttu-id="cd505-103">Le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] propose des annotations que vous pouvez utiliser afin de faire en sorte que les packages s'auto-documentent et soient ainsi plus faciles à comprendre et à gérer.</span><span class="sxs-lookup"><span data-stu-id="cd505-103">The [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer provides annotations, which you can use to make packages self-documenting and easier to understand and maintain.</span></span> <span data-ttu-id="cd505-104">Vous pouvez ajouter des annotations au flux de contrôle, au flux de données et aux surfaces de dessin du gestionnaire d'événements du concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cd505-104">You can add annotations to the control flow, data flow, and event handler design surfaces of [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="cd505-105">Les annotations peuvent contenir n'importe quel type de texte et sont utiles pour ajouter des étiquettes, des commentaires et autres informations descriptives à un package.</span><span class="sxs-lookup"><span data-stu-id="cd505-105">The annotations can contain any type of text, and they are useful for adding labels, comments, and other descriptive information to a package.</span></span> <span data-ttu-id="cd505-106">Les annotations sont disponibles uniquement au moment de la conception.</span><span class="sxs-lookup"><span data-stu-id="cd505-106">Annotations are a design-time feature only.</span></span> <span data-ttu-id="cd505-107">Par exemple, elles ne sont pas écrites dans les fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="cd505-107">For example, they are not written to logs.</span></span>  
  
 <span data-ttu-id="cd505-108">Lorsque vous appuyez sur Entrée, le texte est renvoyé à la ligne suivante.</span><span class="sxs-lookup"><span data-stu-id="cd505-108">When you press ENTER, the text wraps to the next line.</span></span> <span data-ttu-id="cd505-109">La taille de la zone d'annotation augmente automatiquement lorsque vous ajoutez des lignes de texte supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="cd505-109">The annotation box automatically increases in size as you add additional lines of text.</span></span> <span data-ttu-id="cd505-110">Les annotations de package sont conservées en texte clair dans la section CDATA du fichier de package.</span><span class="sxs-lookup"><span data-stu-id="cd505-110">Package annotations are persisted as clear text in the CDATA section of the package file.</span></span>  
  
 <span data-ttu-id="cd505-111">Pour plus d’informations sur les modifications du format du fichier de package, consultez [Format de package SSIS](../../2014/integration-services/ssis-package-format.md).</span><span class="sxs-lookup"><span data-stu-id="cd505-111">For more information about changes to the format of the package file, see [SSIS Package Format](../../2014/integration-services/ssis-package-format.md).</span></span>  
  
 <span data-ttu-id="cd505-112">Lorsque vous enregistrez le package, le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] enregistre les annotations dans le package.</span><span class="sxs-lookup"><span data-stu-id="cd505-112">When you save the package, [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer saves the annotations in the package.</span></span>  
  
### <a name="to-add-an-annotation-to-a-package"></a><span data-ttu-id="cd505-113">Pour ajouter une annotation à un package</span><span class="sxs-lookup"><span data-stu-id="cd505-113">To add an annotation to a package</span></span>  
  
-   [<span data-ttu-id="cd505-114">Ajouter une annotation à un package</span><span class="sxs-lookup"><span data-stu-id="cd505-114">Add an Annotation to a Package</span></span>](../../2014/integration-services/add-an-annotation-to-a-package.md)  
  
  
