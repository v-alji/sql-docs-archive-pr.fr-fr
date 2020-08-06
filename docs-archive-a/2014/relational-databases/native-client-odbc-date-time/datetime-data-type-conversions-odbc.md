---
title: conversions de type de données DateTime (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- conversions [ODBC]
- bindings [ODBC]
- ODBC, bindings and conversions
ms.assetid: 66b9d282-c88d-40e5-93c2-fd5499a74458
author: rothja
ms.author: jroth
ms.openlocfilehash: 142e4388cb87055ddbc6faa7d5b1a92a627738c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612287"
---
# <a name="datetime-data-type-conversions-odbc"></a><span data-ttu-id="ccd7d-102">Conversions du type de données datetime (ODBC)</span><span class="sxs-lookup"><span data-stu-id="ccd7d-102">datetime Data Type Conversions (ODBC)</span></span>
  <span data-ttu-id="ccd7d-103">Les conversions suivantes sont déjà définies par ODBC ou constituent une extension cohérente d'ODBC.</span><span class="sxs-lookup"><span data-stu-id="ccd7d-103">The following conversions are either already defined by ODBC or are a consistent extension of ODBC.</span></span> <span data-ttu-id="ccd7d-104">Les conversions fournies par chaque fournisseur sont déterminées par la communauté servie par le fournisseur, et en conséquence il existe souvent des incohérences entre les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="ccd7d-104">The conversions supplied by each provider are determined by the community served by the provider, and there are often inconsistencies between providers as a result.</span></span> <span data-ttu-id="ccd7d-105">Les valeurs entre crochets ([ et ]) sont facultatives.</span><span class="sxs-lookup"><span data-stu-id="ccd7d-105">Values in square brackets are optional.</span></span>  
  
-   <span data-ttu-id="ccd7d-106">Le format des chaînes datetime est 'aaaa-mm-jj[ hh:mm:ss[.9999999][ plus/moins hh:mm]]'</span><span class="sxs-lookup"><span data-stu-id="ccd7d-106">The format of datetime strings is 'yyyy-mm-dd[ hh:mm:ss[.9999999][ plus/minus hh:mm]]'</span></span>  
  
-   <span data-ttu-id="ccd7d-107">Le format des chaînes time est 'hh:mm:ss[.9999999]'</span><span class="sxs-lookup"><span data-stu-id="ccd7d-107">The format of time strings is 'hh:mm:ss[.9999999]'</span></span>  
  
-   <span data-ttu-id="ccd7d-108">Le format des chaînes date est 'aaaa-mm-jj'</span><span class="sxs-lookup"><span data-stu-id="ccd7d-108">The format of date strings is 'yyyy-mm-dd'</span></span>  
  
 <span data-ttu-id="ccd7d-109">Les conversions de chaînes autorisent une souplesse en matière d'espace et de largeur de champ.</span><span class="sxs-lookup"><span data-stu-id="ccd7d-109">Conversions from strings allow flexibility in white space and field width.</span></span> <span data-ttu-id="ccd7d-110">Pour plus d’informations, consultez la section « formats de données : chaînes et littéraux » de [type de données prise en charge des améliorations de date et d’heure ODBC](data-type-support-for-odbc-date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="ccd7d-110">For more information, see the "Data Formats: Strings and Literals" section of [Data Type Support for ODBC Date and Time Improvements](data-type-support-for-odbc-date-and-time-improvements.md).</span></span>  
  
 <span data-ttu-id="ccd7d-111">Les règles suivantes sont les règles générales de conversion :</span><span class="sxs-lookup"><span data-stu-id="ccd7d-111">The following are general conversion rules:</span></span>  
  
-   <span data-ttu-id="ccd7d-112">Si aucune heure n'est fournie mais le récepteur peut stocker l'heure, l'heure est définie avec la valeur zéro.</span><span class="sxs-lookup"><span data-stu-id="ccd7d-112">If no time is present but the receiver can store time, the time is set to zero.</span></span>  
  
-   <span data-ttu-id="ccd7d-113">Si aucune date n'est présente mais que le récepteur peut stocker la date, la date courante est utilisée.</span><span class="sxs-lookup"><span data-stu-id="ccd7d-113">If no date is present but the receiver can store date, the current date is used.</span></span>  
  
-   <span data-ttu-id="ccd7d-114">Si aucun fuseau n'est présent dans le type de données que le client utilise mais que le serveur peut stocker le fuseau, la date est stockée dans le fuseau horaire du client.</span><span class="sxs-lookup"><span data-stu-id="ccd7d-114">If no timezone is present in the data type that the client is using but the server can store timezone, the date is stored in the client timezone.</span></span> <span data-ttu-id="ccd7d-115">Notez la différence avec le comportement du serveur.</span><span class="sxs-lookup"><span data-stu-id="ccd7d-115">Note that this differs from the server behavior.</span></span>  
  
-   <span data-ttu-id="ccd7d-116">Si aucun fuseau n'est présent dans le type de serveur mais que le type de client possède un fuseau, l'heure est convertie en heure UTC avant d'être stockée sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="ccd7d-116">If no timezone is present in the server type but the client type has a timezone, time is converted to UTC before being stored on the server.</span></span>  
  
-   <span data-ttu-id="ccd7d-117">Si l'heure est présente mais que le récepteur ne peut pas la stocker, le composant heure est ignoré.</span><span class="sxs-lookup"><span data-stu-id="ccd7d-117">If time is present but the receiver cannot store time, the time component is ignored.</span></span>  
  
-   <span data-ttu-id="ccd7d-118">Si une date est présente mais que le récepteur ne peut pas la stocker, le composant date est ignoré.</span><span class="sxs-lookup"><span data-stu-id="ccd7d-118">If a date is present but the receiver cannot store the date, the date component is ignored.</span></span>  
  
-   <span data-ttu-id="ccd7d-119">Si la troncation de secondes ou de fractions de seconde se produit lors de la conversion de C en SQL, un enregistrement de diagnostic est généré avec la valeur SQLSTATE 22008 et le message « Dépassement de la capacité du champ datetime ».</span><span class="sxs-lookup"><span data-stu-id="ccd7d-119">If truncation of seconds or fractional seconds occurs when converting from C to SQL, a diagnostic record is generated with SQLSTATE 22008 and the message "Datetime field overflow".</span></span>  
  
-   <span data-ttu-id="ccd7d-120">Si la troncation de secondes ou de fractions de seconde se produit lors de la conversion de SQL en C, un enregistrement de diagnostic est généré avec la valeur SQLSTATE 01S07 et le message « Troncation fractionnelle ».</span><span class="sxs-lookup"><span data-stu-id="ccd7d-120">If truncation of seconds or fractional seconds occurs when converting from SQL to C, a diagnostic record is generated with SQLSTATE 01S07 and the message "Fractional truncation".</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ccd7d-121">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="ccd7d-121">In This Section</span></span>  
 [<span data-ttu-id="ccd7d-122">Conversions de C à SQL</span><span class="sxs-lookup"><span data-stu-id="ccd7d-122">Conversions from C to SQL</span></span>](datetime-data-type-conversions-from-c-to-sql.md)  
 <span data-ttu-id="ccd7d-123">Répertorie les problèmes à prendre en compte lorsque vous effectuez une conversion de types C en types [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date/time.</span><span class="sxs-lookup"><span data-stu-id="ccd7d-123">Lists issues to consider when you convert from C types to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data/time types.</span></span>  
  
 [<span data-ttu-id="ccd7d-124">Conversions de SQL à C</span><span class="sxs-lookup"><span data-stu-id="ccd7d-124">Conversions from SQL to C</span></span>](datetime-data-type-conversions-from-sql-to-c.md)  
 <span data-ttu-id="ccd7d-125">Répertorie les problèmes à prendre en compte lorsque vous effectuez une conversion de types [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date/time en types C.</span><span class="sxs-lookup"><span data-stu-id="ccd7d-125">Lists issues to consider when you convert from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data/time types to C types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccd7d-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ccd7d-126">See Also</span></span>  
 [<span data-ttu-id="ccd7d-127">Améliorations de la date et de l’heure &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="ccd7d-127">Date and Time Improvements &#40;ODBC&#41;</span></span>](date-and-time-improvements-odbc.md)  
  
  
