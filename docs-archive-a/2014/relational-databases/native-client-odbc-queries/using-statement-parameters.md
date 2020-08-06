---
title: Utilisation des paramètres d’instruction | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, parameters
- parameters [SQL Server Native Client], ODBC
- ODBC, parameters
- statements [ODBC], parameters
- parameter markers [ODBC]
- SQL Server Native Client ODBC driver, statements
- ODBC applications, statements
ms.assetid: 2427d886-ec6c-49d7-b0b6-0d998b64cdb9
author: rothja
ms.author: jroth
ms.openlocfilehash: 7b7e207416e60af94efd59555980a0edff68a38b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600847"
---
# <a name="using-statement-parameters"></a><span data-ttu-id="c053b-102">Utilisation de paramètres d'instruction</span><span class="sxs-lookup"><span data-stu-id="c053b-102">Using Statement Parameters</span></span>
  <span data-ttu-id="c053b-103">Un paramètre est une variable dans une instruction SQL qui peut permettre à une application ODBC d'effectuer les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="c053b-103">A parameter is a variable in an SQL statement that can enable an ODBC application to:</span></span>  
  
-   <span data-ttu-id="c053b-104">fournir de manière efficace des valeurs pour les colonnes d'une table ;</span><span class="sxs-lookup"><span data-stu-id="c053b-104">Efficiently provide values for columns in a table.</span></span>  
  
-   <span data-ttu-id="c053b-105">améliorer l'interaction de l'utilisateur lors de la construction de critères de requête ;</span><span class="sxs-lookup"><span data-stu-id="c053b-105">Enhance user interaction in constructing query criteria.</span></span>  
  
-   <span data-ttu-id="c053b-106">Gérer les données **Text**, **ntext**et **image** et les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types de données C spécifiques.</span><span class="sxs-lookup"><span data-stu-id="c053b-106">Manage **text**, **ntext**, and **image** data and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific C data types.</span></span>  
  
 <span data-ttu-id="c053b-107">Par exemple, une table de **pièces** contient des colonnes nommées **partid**, **Description**et **Price**.</span><span class="sxs-lookup"><span data-stu-id="c053b-107">For example, a **Parts** table has columns named **PartID**, **Description**, and **Price**.</span></span> <span data-ttu-id="c053b-108">L'ajout d'un article sans paramètres requiert la construction d'une instruction SQL telle que :</span><span class="sxs-lookup"><span data-stu-id="c053b-108">To add a part without parameters requires constructing an SQL statement such as:</span></span>  
  
```  
INSERT INTO Parts (PartID, Description, Price) VALUES (2100, 'Drive shaft', 50.00)  
```  
  
 <span data-ttu-id="c053b-109">Bien que cette instruction soit acceptable pour insérer une ligne avec un jeu connu de valeurs, elle est maladroite lorsqu'une application doit insérer plusieurs lignes.</span><span class="sxs-lookup"><span data-stu-id="c053b-109">Although this statement is acceptable for inserting one row with a known set of values, it is awkward when an application is required to insert several rows.</span></span> <span data-ttu-id="c053b-110">Pour résoudre ce problème, ODBC laisse une application remplacer toute valeur de données dans une instruction SQL par un fabricant de paramètre.</span><span class="sxs-lookup"><span data-stu-id="c053b-110">ODBC addresses this by letting an application to replace any data value in an SQL statement by a parameter maker.</span></span> <span data-ttu-id="c053b-111">Cela est dénoté par un point d'interrogation (?).</span><span class="sxs-lookup"><span data-stu-id="c053b-111">This is denoted by a question mark (?).</span></span> <span data-ttu-id="c053b-112">Dans l'exemple suivant, trois valeurs de données sont remplacées par des marqueurs de paramètres :</span><span class="sxs-lookup"><span data-stu-id="c053b-112">In the following example, three data values are replaced with parameter markers:</span></span>  
  
```  
INSERT INTO Parts (PartID, Description, Price) VALUES (?, ?, ?)  
```  
  
 <span data-ttu-id="c053b-113">Les marqueurs de paramètres sont ensuite liés à des variables d'applications.</span><span class="sxs-lookup"><span data-stu-id="c053b-113">The parameter markers are then bound to application variables.</span></span> <span data-ttu-id="c053b-114">Pour insérer une nouvelle ligne, l'application doit uniquement définir les valeurs des variables et exécuter l'instruction.</span><span class="sxs-lookup"><span data-stu-id="c053b-114">To insert a new row, the application has only to set the values of the variables and execute the statement.</span></span> <span data-ttu-id="c053b-115">Le pilote extrait ensuite les valeurs actuelles des variables et les envoie à la source de données.</span><span class="sxs-lookup"><span data-stu-id="c053b-115">The driver then retrieves the current values of the variables and sends them to the data source.</span></span> <span data-ttu-id="c053b-116">Si l'instruction est exécutée plusieurs fois, l'application peut rendre le processus encore plus efficace en préparant l'instruction.</span><span class="sxs-lookup"><span data-stu-id="c053b-116">If the statement is executed multiple times, the application can make the process even more efficient by preparing the statement.</span></span>  
  
 <span data-ttu-id="c053b-117">Chaque marqueur de paramètre est référencé par son nombre ordinal assigné aux paramètres de gauche à droite.</span><span class="sxs-lookup"><span data-stu-id="c053b-117">Each parameter marker is referenced by its ordinal number assigned to the parameters from left to right.</span></span> <span data-ttu-id="c053b-118">Le marqueur de paramètre situé le plus à gauche dans une instruction SQL a la valeur ordinale 1 ; le suivant a la valeur ordinale 2, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="c053b-118">The leftmost parameter marker in an SQL statement has an ordinal value of 1; the next one is ordinal 2, and so on.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c053b-119">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="c053b-119">In This Section</span></span>  
  
-   [<span data-ttu-id="c053b-120">Liaison de paramètres</span><span class="sxs-lookup"><span data-stu-id="c053b-120">Binding Parameters</span></span>](using-statement-parameters-binding-parameters.md)  
  
## <a name="see-also"></a><span data-ttu-id="c053b-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c053b-121">See Also</span></span>  
 [<span data-ttu-id="c053b-122">Exécution de requêtes &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="c053b-122">Executing Queries &#40;ODBC&#41;</span></span>](executing-queries-odbc.md)  
  
  
