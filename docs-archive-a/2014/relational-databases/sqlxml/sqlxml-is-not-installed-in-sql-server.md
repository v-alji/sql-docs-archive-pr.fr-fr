---
title: SQLXML n’est pas installé dans SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: 3dbb4f65-41de-48b8-ad62-47c9d7932de3
author: rothja
ms.author: jroth
ms.openlocfilehash: ffa4cfd8b18dbfd9b4ba05599e2a973ac5f6e888
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611658"
---
# <a name="sqlxml-is-not-installed-in-sql-server"></a><span data-ttu-id="ff647-102">SQLXML n'est pas installé dans SQL Server</span><span class="sxs-lookup"><span data-stu-id="ff647-102">SQLXML Is Not Installed in SQL Server</span></span>
  <span data-ttu-id="ff647-103">Avant [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], SQLXML 4.0 était fourni avec [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et faisait partie de l'installation par défaut de toutes les versions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], à l'exception de [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff647-103">Before [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], SQLXML 4.0 was released with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and was part of the default installation of all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versions except for [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span> <span data-ttu-id="ff647-104">À partir de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], la dernière version de SQLXML (SQLXML 4.0 SP1) n'est plus incluse dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff647-104">Starting with [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the latest version of SQLXML (SQLXML 4.0 SP1) is no longer included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ff647-105">Pour installer SQLXML 4,0 SP1 lorsqu’il est disponible, téléchargez-le à partir de l' [emplacement d’installation de SQLXML SP1](https://www.microsoft.com/download/details.aspx?id=44272).</span><span class="sxs-lookup"><span data-stu-id="ff647-105">To install SQLXML 4.0 SP1 when it is available, download it from [Install Location for SQLXML SP1](https://www.microsoft.com/download/details.aspx?id=44272).</span></span>  
  
 <span data-ttu-id="ff647-106">Si une application est exécutée sur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et nécessite SQLXML 4.0, et si l'ordinateur ne dispose pas de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], vous devez télécharger et installer SQLXML 4.0 SP1.</span><span class="sxs-lookup"><span data-stu-id="ff647-106">If an application runs on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and requires SQLXML 4.0, and if the computer does not have [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], you must download and install SQLXML 4.0 SP1.</span></span>  
  
## <a name="sqlxml-40-sp1-behavior-with-new-data-types-using-sqloledb-and-sql-server-native-client-ole-db-provider"></a><span data-ttu-id="ff647-107">Comportement de SQLXML 4.0 SP1 avec les nouveaux types de données utilisant SQLOLEDB et le fournisseur OLE DB SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="ff647-107">SQLXML 4.0 SP1 Behavior with New Data Types Using SQLOLEDB and SQL Server Native Client OLE DB Provider</span></span>  
 [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] <span data-ttu-id="ff647-108">introduit les types de données suivants que les développeurs qui utilisent SQLXML peuvent souhaiter exploiter :</span><span class="sxs-lookup"><span data-stu-id="ff647-108">introduces the following data types, which developers using SQLXML might want to use:</span></span>  
  
-   `Date`  
  
-   `Time`  
  
-   `DateTime2`  
  
-   `DateTimeOffset`  
  
 <span data-ttu-id="ff647-109">Lors de l'utilisation de SQLXML 4.0 SP1 avec SQLOLEDB (issu de Windows Data Access Components, anciennement connu sous le nom Microsoft Data Access Components) ou le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], ces nouveaux types apparaîtront au développeur sous la forme de chaînes.</span><span class="sxs-lookup"><span data-stu-id="ff647-109">When using SQLXML 4.0 SP1 with either SQLOLEDB (from Windows Data Access Components, formerly Microsoft Data Access Components) or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], these new types will appear as strings to a developer.</span></span> <span data-ttu-id="ff647-110">SQLXML 4.0 SP1 activera ces quatre nouveaux types de données sous la forme de types scalaires intégrés lors d'une utilisation avec le fournisseur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider 11.0.</span><span class="sxs-lookup"><span data-stu-id="ff647-110">SQLXML 4.0 SP1 will enable these four new data types as built-in scalar types when used with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider 11.0.</span></span> <span data-ttu-id="ff647-111">Tant que vous n'aurez pas téléchargé SQLXML 4.0 SP1, le mappage de ces types en types autres que chaîne risque de provoquer la troncation de certaines données.</span><span class="sxs-lookup"><span data-stu-id="ff647-111">Until you download SQLXML 4.0 SP1, mapping these types to non-string types might cause truncation of some data.</span></span> <span data-ttu-id="ff647-112">Par exemple, `DateTime2` le mappage à `xsd:date` entraîne la troncation des données à la [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] `DateTime` précision de 3,33 millisecondes.</span><span class="sxs-lookup"><span data-stu-id="ff647-112">For example, mapping `DateTime2` to `xsd:date` will cause data to be truncated to the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] `DateTime` precision of 3.33 milliseconds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff647-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ff647-113">See Also</span></span>  
 [<span data-ttu-id="ff647-114">Concepts de la programmation SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="ff647-114">SQLXML 4.0 Programming Concepts</span></span>](sqlxml-4-0-programming-concepts.md)  
  
  
