---
title: Modification d’un assembly | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- assemblies [CLR integration], modifying
- permissions [CLR integration]
- altering assemblies
- ALTER ASSEMBLY statement
ms.assetid: 9e765fbd-f339-473c-8537-22f478e79696
author: rothja
ms.author: jroth
ms.openlocfilehash: c22ca979675d3b7f263e3bc6de0c41c134a1abcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704172"
---
# <a name="altering-an-assembly"></a><span data-ttu-id="26853-102">Modification d'un assembly</span><span class="sxs-lookup"><span data-stu-id="26853-102">Altering an Assembly</span></span>
  <span data-ttu-id="26853-103">Les assemblys inscrits dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] peuvent être mis à jour à partir d'une version plus récente via l'instruction ALTER ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="26853-103">Assemblies that have been registered in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] can be updated from a more recent version using the ALTER ASSEMBLY statement.</span></span> <span data-ttu-id="26853-104">Pour mettre à jour un assembly, utilisez l'instruction ALTER ASSEMBLY avec la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="26853-104">To update an assembly, use the ALTER ASSEMBLY statement with the following syntax:</span></span>  
  
```  
ALTER ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
```  
  
 <span data-ttu-id="26853-105">ALTER ASSEMBLY n'interrompt pas les processus en cours d'exécution qui utilisent l'assembly ; ces processus continuent à s'exécuter avec l'assembly non modifié.</span><span class="sxs-lookup"><span data-stu-id="26853-105">ALTER ASSEMBLY does not disrupt currently running processes that are using the assembly; the processes continue executing with the unaltered assembly.</span></span> <span data-ttu-id="26853-106">ALTER ASSEMBLY ne peut pas être utilisé pour modifier les signatures des fonctions CLR (Common Language Runtime), des fonctions d'agrégation, des procédures stockées et des déclencheurs.</span><span class="sxs-lookup"><span data-stu-id="26853-106">ALTER ASSEMBLY cannot be used to change the signatures of common language runtime (CLR) functions, aggregate functions, stored procedures, and triggers.</span></span> <span data-ttu-id="26853-107">De nouvelles méthodes publiques peuvent être ajoutées à l'assembly, les méthodes privées peuvent être modifiées librement ; par ailleurs, les méthodes publiques peuvent être modifiées à condition que les signatures ou les attributs ne soient pas modifiés.</span><span class="sxs-lookup"><span data-stu-id="26853-107">New public methods can be added to the assembly, private methods can be modified in any way, and public methods can be modified as long as signatures or attributes are not changed.</span></span> <span data-ttu-id="26853-108">Les champs qui se trouvent dans un type défini par l'utilisateur sérialisé de façon native (notamment les membres de données ou les classes de base) ne peuvent pas être modifiés via ALTER ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="26853-108">Fields that are contained within a native-serialized user-defined type, including data members or base classes, cannot be changed by using ALTER ASSEMBLY.</span></span> <span data-ttu-id="26853-109">Aucune autre modification n'est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="26853-109">All other changes are unsupported.</span></span> <span data-ttu-id="26853-110">Pour plus d’informations, consultez [ALTER assembly &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="26853-110">For more information, see [ALTER ASSEMBLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span></span>  
  
## <a name="changing-the-permission-set-of-an-assembly"></a><span data-ttu-id="26853-111">Modification du jeu d'autorisations d'un assembly</span><span class="sxs-lookup"><span data-stu-id="26853-111">Changing the Permission Set of an Assembly</span></span>  
 <span data-ttu-id="26853-112">Le jeu d'autorisations d'un assembly peut également être modifié à l'aide de l'instruction ALTER ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="26853-112">The permission set of an assembly can also be changed using the ALTER ASSEMBLY statement.</span></span> <span data-ttu-id="26853-113">L'instruction suivante modifie le jeu d'autorisations de l'assembly SQLCLRTest en le remplaçant par `EXTERNAL_ACCESS`.</span><span class="sxs-lookup"><span data-stu-id="26853-113">The following statement changes the permission set of the SQLCLRTest assembly to `EXTERNAL_ACCESS`.</span></span>  
  
```  
ALTER ASSEMBLY SQLCLRTest  
WITH PERMISSION_SET = EXTERNAL_ACCESS   
```  
  
 <span data-ttu-id="26853-114">Si le jeu d'autorisations d'un assembly est modifié de `SAFE` à `EXTERNAL_ACCESS` ou `UNSAFE`, une clé asymétrique et la connexion correspondante avec l'autorisation `EXTERNAL ACCESS ASSEMBLY` ou l'autorisation `UNSAFE ASSEMBLY` pour l'assembly doit être créée au préalable.</span><span class="sxs-lookup"><span data-stu-id="26853-114">If the permission set of an assembly is being changed from `SAFE` to `EXTERNAL_ACCESS` or `UNSAFE`, an asymmetric key and corresponding login with `EXTERNAL ACCESS ASSEMBLY` permission or `UNSAFE ASSEMBLY` permission for the assembly must first be created.</span></span> <span data-ttu-id="26853-115">Pour plus d’informations, consultez [Creating an Assembly](creating-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="26853-115">For more information, see [Creating an Assembly](creating-an-assembly.md).</span></span>  
  
## <a name="adding-the-source-code-of-an-assembly"></a><span data-ttu-id="26853-116">Ajout du code source d'un assembly</span><span class="sxs-lookup"><span data-stu-id="26853-116">Adding the Source Code of an Assembly</span></span>  
 <span data-ttu-id="26853-117">La clause ADD FILE de la syntaxe ALTER ASSEMBLY n'est pas présente dans CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="26853-117">The ADD FILE clause in the ALTER ASSEMBLY syntax is not present in CREATE ASSEMBLY.</span></span> <span data-ttu-id="26853-118">Vous pouvez l'utiliser pour ajouter le code source ou tout autre fichier associé à un assembly.</span><span class="sxs-lookup"><span data-stu-id="26853-118">You can use it to add source code or any other files associated with an assembly.</span></span> <span data-ttu-id="26853-119">Les fichiers sont copiés depuis leur emplacement d'origine et stockés dans les tables système de la base de données.</span><span class="sxs-lookup"><span data-stu-id="26853-119">The files are copied from their original locations and stored in system tables in the database.</span></span> <span data-ttu-id="26853-120">Le code source et autres fichiers est toujours à portée de main dans l'éventualité où vous deviez recréer ou documenter la version actuelle de l'UDT.</span><span class="sxs-lookup"><span data-stu-id="26853-120">This ensures that you always have source code or other files on hand should you ever need to re-create or document the current version of the UDT.</span></span>  
  
 <span data-ttu-id="26853-121">L'instruction suivante ajoute le code source de la classe Point.cs pour le type défini par l'utilisateur Point.</span><span class="sxs-lookup"><span data-stu-id="26853-121">The following statement adds the Point.cs class source code for the Point UDT.</span></span> <span data-ttu-id="26853-122">Le texte contenu dans le fichier Point.cs est alors copié et stocké dans la base de données sous le nom PointSource.</span><span class="sxs-lookup"><span data-stu-id="26853-122">This copies the text contained in the Point.cs file and stores it in the database under the name "PointSource".</span></span>  
  
 `ALTER ASSEMBLY Point`  
  
 `ADD FILE FROM 'C:\Projects\Point\Point.cs' AS PointSource`  
  
## <a name="see-also"></a><span data-ttu-id="26853-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="26853-123">See Also</span></span>  
 <span data-ttu-id="26853-124">[Gestion des assemblys d’intégration du CLR](managing-clr-integration-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="26853-124">[Managing CLR Integration Assemblies](managing-clr-integration-assemblies.md) </span></span>  
 <span data-ttu-id="26853-125">[Création d’un assembly](creating-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="26853-125">[Creating an Assembly](creating-an-assembly.md) </span></span>  
 <span data-ttu-id="26853-126">[Suppression d’un assembly](dropping-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="26853-126">[Dropping an Assembly](dropping-an-assembly.md) </span></span>  
 [<span data-ttu-id="26853-127">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="26853-127">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-assembly-transact-sql)  
  
  
