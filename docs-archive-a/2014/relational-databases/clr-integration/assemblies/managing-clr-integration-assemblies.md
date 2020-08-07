---
title: Gestion des assemblys d’intégration du CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- database objects [CLR integration], assemblies
- common language runtime [SQL Server], assemblies
- assemblies [CLR integration], managing
ms.assetid: bdbbf325-14f6-460e-a35a-d3861d3c961e
author: rothja
ms.author: jroth
ms.openlocfilehash: 191ccd73ca42ef4c26291e6de88f5f2b0cf565ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704156"
---
# <a name="managing-clr-integration-assemblies"></a><span data-ttu-id="4e117-102">Gestion des assemblys d'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="4e117-102">Managing CLR Integration Assemblies</span></span>
  <span data-ttu-id="4e117-103">Le code managé est compilé, puis déployé dans des unités appelées « assemblys ».</span><span class="sxs-lookup"><span data-stu-id="4e117-103">Managed code is compiled and then deployed in units called an assembly.</span></span> <span data-ttu-id="4e117-104">Un assembly est fourni sous la forme d'une DLL ou d'un fichier exécutable (.exe).</span><span class="sxs-lookup"><span data-stu-id="4e117-104">An assembly is packaged as a DLL or executable (.exe) file.</span></span> <span data-ttu-id="4e117-105">Alors qu'un fichier exécutable peut s'exécuter seul, une DLL doit être hébergée dans une application existante.</span><span class="sxs-lookup"><span data-stu-id="4e117-105">While an executable file can run on its own, a DLL must be hosted in an existing application.</span></span> <span data-ttu-id="4e117-106">Les assemblys DLL managés peuvent être chargés et hébergés par [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4e117-106">Managed DLL assemblies can be loaded into and hosted by [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)].</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="4e117-107">base de données à l’aide de l’instruction CREATe ASSEMBLy, avant qu’elle ne puisse être chargée dans le processus et utilisée.</span><span class="sxs-lookup"><span data-stu-id="4e117-107">database using the CREATE ASSEMBLY statement, before it can be loaded in the process and used.</span></span> <span data-ttu-id="4e117-108">Les assemblys peuvent également être mis à jour à partir d'une version plus récente au moyen de l'instruction ALTER ASSEMBLY ou supprimés de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] avec l'instruction DROP ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="4e117-108">Assemblies can also be updated from a more recent version using the ALTER ASSEMBLY statement, or removed from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] using the DROP ASSEMBLY statement.</span></span>  
  
 <span data-ttu-id="4e117-109">Les informations relatives aux assemblys sont stockées dans la table `sys.assembly_files`, dans la base de données où l'assembly a été installé.</span><span class="sxs-lookup"><span data-stu-id="4e117-109">Assembly information is stored in the `sys.assembly_files` table in the database where the assembly has been installed.</span></span> <span data-ttu-id="4e117-110">La `sys.assembly_files` table contient les colonnes suivantes.</span><span class="sxs-lookup"><span data-stu-id="4e117-110">The `sys.assembly_files` table contains the following columns.</span></span>  
  
|<span data-ttu-id="4e117-111">Colonne</span><span class="sxs-lookup"><span data-stu-id="4e117-111">Column</span></span>|<span data-ttu-id="4e117-112">Description</span><span class="sxs-lookup"><span data-stu-id="4e117-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="4e117-113">assembly_id</span><span class="sxs-lookup"><span data-stu-id="4e117-113">assembly_id</span></span>|<span data-ttu-id="4e117-114">Identificateur défini pour l'assembly.</span><span class="sxs-lookup"><span data-stu-id="4e117-114">The identifier defined for the assembly.</span></span> <span data-ttu-id="4e117-115">Ce numéro est affecté à tous les objets se rapportant au même assembly.</span><span class="sxs-lookup"><span data-stu-id="4e117-115">This number is assigned to all objects relating to the same assembly.</span></span>|  
|<span data-ttu-id="4e117-116">name</span><span class="sxs-lookup"><span data-stu-id="4e117-116">name</span></span>|<span data-ttu-id="4e117-117">Nom de l'objet.</span><span class="sxs-lookup"><span data-stu-id="4e117-117">The name of the object.</span></span>|  
|<span data-ttu-id="4e117-118">file_id</span><span class="sxs-lookup"><span data-stu-id="4e117-118">file_id</span></span>|<span data-ttu-id="4e117-119">Numéro identifiant chaque objet (le premier objet associé à un `assembly_id` possède la valeur 1).</span><span class="sxs-lookup"><span data-stu-id="4e117-119">A number identifying each object, with the first object associated with a given `assembly_id` being given the value of 1.</span></span> <span data-ttu-id="4e117-120">Si plusieurs objets sont associés au même `assembly_id`, chaque valeur `file_id` suivante est alors incrémentée de 1.</span><span class="sxs-lookup"><span data-stu-id="4e117-120">If multiple objects are associated with the same `assembly_id`, then each subsequent `file_id` value is incremented by 1.</span></span>|  
|<span data-ttu-id="4e117-121">contenu</span><span class="sxs-lookup"><span data-stu-id="4e117-121">content</span></span>|<span data-ttu-id="4e117-122">Représentation hexadécimale de l'assembly ou du fichier.</span><span class="sxs-lookup"><span data-stu-id="4e117-122">The hexadecimal representation of the assembly or file.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="4e117-123">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="4e117-123">In This Section</span></span>  
 [<span data-ttu-id="4e117-124">Création d'un assembly</span><span class="sxs-lookup"><span data-stu-id="4e117-124">Creating an Assembly</span></span>](creating-an-assembly.md)  
 <span data-ttu-id="4e117-125">Aborde la création des assemblys SAFE, EXTERNAL_ACCESS et UNSAFE CLR dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e117-125">Discusses creating SAFE, EXTERNAL_ACCESS, and UNSAFE CLR assemblies in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="4e117-126">Modification d'un assembly</span><span class="sxs-lookup"><span data-stu-id="4e117-126">Altering an Assembly</span></span>](altering-an-assembly.md)  
 <span data-ttu-id="4e117-127">Décrit la mise à jour des assemblys du CLR dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e117-127">Describes updating CLR assemblies in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="4e117-128">Suppression d'un assembly</span><span class="sxs-lookup"><span data-stu-id="4e117-128">Dropping an Assembly</span></span>](dropping-an-assembly.md)  
 <span data-ttu-id="4e117-129">Décrit la suppression des assemblys du CLR de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e117-129">Discusses dropping CLR assemblies from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e117-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4e117-130">See Also</span></span>  
 <span data-ttu-id="4e117-131">[Sécurité de l’intégration du CLR](../security/clr-integration-security.md) </span><span class="sxs-lookup"><span data-stu-id="4e117-131">[CLR Integration Security](../security/clr-integration-security.md) </span></span>  
 [<span data-ttu-id="4e117-132">Sécurité d'accès du code de l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="4e117-132">CLR Integration Code Access Security</span></span>](../security/clr-integration-code-access-security.md)  
  
  
