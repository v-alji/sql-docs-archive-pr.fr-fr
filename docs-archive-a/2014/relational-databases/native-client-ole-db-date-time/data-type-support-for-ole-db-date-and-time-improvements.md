---
title: Prise en charge des types de données pour les améliorations de date et d’heure OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- date/time [OLE DB], data type support
- OLE DB, date/time improvements
ms.assetid: d40e3fd6-9057-4371-8236-95cef300603e
author: rothja
ms.author: jroth
ms.openlocfilehash: 834583fdec63a8f613e623c239f9c3a1c9398950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706415"
---
# <a name="data-type-support-for-ole-db-date-and-time-improvements"></a><span data-ttu-id="6562b-102">Prise en charge des types de données pour les améliorations de date et d’heure OLE DB</span><span class="sxs-lookup"><span data-stu-id="6562b-102">Data Type Support for OLE DB Date and Time Improvements</span></span>
  <span data-ttu-id="6562b-103">Cette rubrique fournit des informations sur les types OLE DB ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client) qui prennent en charge les types de données de date/heure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6562b-103">This topic provides information about OLE DB ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client) types that support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date/time data types.</span></span>  
  
## <a name="data-type-mapping-in-rowsets-and-parameters"></a><span data-ttu-id="6562b-104">Mappage de type de données dans les ensembles de lignes et les paramètres</span><span class="sxs-lookup"><span data-stu-id="6562b-104">Data Type Mapping in Rowsets and Parameters</span></span>  
 <span data-ttu-id="6562b-105">OLE DB fournit deux nouveaux types de données pour prendre en charge les nouveaux types de serveurs : DBTYPE_DBTIME2 et DBTYPE_DBTIMESTAMPOFFSET.</span><span class="sxs-lookup"><span data-stu-id="6562b-105">OLE DB provides two new data types to support the new server types: DBTYPE_DBTIME2 and DBTYPE_DBTIMESTAMPOFFSET.</span></span> <span data-ttu-id="6562b-106">Le tableau ci-dessous illustre le mappage complet des types de serveurs :</span><span class="sxs-lookup"><span data-stu-id="6562b-106">The following table shows the complete server type mapping:</span></span>  
  
|<span data-ttu-id="6562b-107">Type de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6562b-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type</span></span>|<span data-ttu-id="6562b-108">Type de données OLE DB</span><span class="sxs-lookup"><span data-stu-id="6562b-108">OLE DB data type</span></span>|<span data-ttu-id="6562b-109">Valeur</span><span class="sxs-lookup"><span data-stu-id="6562b-109">Value</span></span>|  
|-----------------------------------------|----------------------|-----------|  
|<span data-ttu-id="6562b-110">DATETIME</span><span class="sxs-lookup"><span data-stu-id="6562b-110">datetime</span></span>|<span data-ttu-id="6562b-111">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="6562b-111">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="6562b-112">135 (oledb.h)</span><span class="sxs-lookup"><span data-stu-id="6562b-112">135 (oledb.h)</span></span>|  
|<span data-ttu-id="6562b-113">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="6562b-113">smalldatetime</span></span>|<span data-ttu-id="6562b-114">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="6562b-114">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="6562b-115">135 (oledb.h)</span><span class="sxs-lookup"><span data-stu-id="6562b-115">135 (oledb.h)</span></span>|  
|<span data-ttu-id="6562b-116">Date</span><span class="sxs-lookup"><span data-stu-id="6562b-116">date</span></span>|<span data-ttu-id="6562b-117">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="6562b-117">DBTYPE_DBDATE</span></span>|<span data-ttu-id="6562b-118">133 (oledb.h)</span><span class="sxs-lookup"><span data-stu-id="6562b-118">133 (oledb.h)</span></span>|  
|<span data-ttu-id="6562b-119">time</span><span class="sxs-lookup"><span data-stu-id="6562b-119">time</span></span>|<span data-ttu-id="6562b-120">DBTYPE_DBTIME2</span><span class="sxs-lookup"><span data-stu-id="6562b-120">DBTYPE_DBTIME2</span></span>|<span data-ttu-id="6562b-121">145 (sqlncli. h)</span><span class="sxs-lookup"><span data-stu-id="6562b-121">145 (sqlncli.h)</span></span>|  
|<span data-ttu-id="6562b-122">datetimeoffset</span><span class="sxs-lookup"><span data-stu-id="6562b-122">datetimeoffset</span></span>|<span data-ttu-id="6562b-123">DBTYPE_DBTIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="6562b-123">DBTYPE_DBTIMESTAMPOFFSET</span></span>|<span data-ttu-id="6562b-124">146 (sqlncli. h)</span><span class="sxs-lookup"><span data-stu-id="6562b-124">146 (sqlncli.h)</span></span>|  
|<span data-ttu-id="6562b-125">datetime2</span><span class="sxs-lookup"><span data-stu-id="6562b-125">datetime2</span></span>|<span data-ttu-id="6562b-126">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="6562b-126">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="6562b-127">135 (oledb.h)</span><span class="sxs-lookup"><span data-stu-id="6562b-127">135 (oledb.h)</span></span>|  
  
## <a name="data-formats-strings-and-literals"></a><span data-ttu-id="6562b-128">Formats de données : chaînes et littéraux</span><span class="sxs-lookup"><span data-stu-id="6562b-128">Data Formats: Strings and Literals</span></span>  
  
|<span data-ttu-id="6562b-129">Type de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6562b-129">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type</span></span>|<span data-ttu-id="6562b-130">Type de données OLE DB</span><span class="sxs-lookup"><span data-stu-id="6562b-130">OLE DB data type</span></span>|<span data-ttu-id="6562b-131">Format de chaîne pour les conversions clientes</span><span class="sxs-lookup"><span data-stu-id="6562b-131">String format for client conversions</span></span>|  
|-----------------------------------------|----------------------|------------------------------------------|  
|<span data-ttu-id="6562b-132">DATETIME</span><span class="sxs-lookup"><span data-stu-id="6562b-132">datetime</span></span>|<span data-ttu-id="6562b-133">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="6562b-133">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="6562b-134">'aaaa-mm-jj hh:mm:ss[.999]'</span><span class="sxs-lookup"><span data-stu-id="6562b-134">'yyyy-mm-dd hh:mm:ss[.999]'</span></span><br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6562b-135">prend en charge jusqu'à trois chiffres de fractions de seconde pour le type Datetime.</span><span class="sxs-lookup"><span data-stu-id="6562b-135">supports up to three fractional second digits for Datetime.</span></span>|  
|<span data-ttu-id="6562b-136">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="6562b-136">smalldatetime</span></span>|<span data-ttu-id="6562b-137">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="6562b-137">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="6562b-138">'aaaa-mm-jj hh:mm:ss'</span><span class="sxs-lookup"><span data-stu-id="6562b-138">'yyyy-mm-dd hh:mm:ss'</span></span><br /><br /> <span data-ttu-id="6562b-139">Ce type de données possède une précision d'une minute.</span><span class="sxs-lookup"><span data-stu-id="6562b-139">This data type has an accuracy of one minute.</span></span> <span data-ttu-id="6562b-140">Le composant des secondes sera égal à zéro en sortie et arrondi par le serveur en entrée.</span><span class="sxs-lookup"><span data-stu-id="6562b-140">The seconds component will be zero on output and will be rounded by the server on input.</span></span>|  
|<span data-ttu-id="6562b-141">Date</span><span class="sxs-lookup"><span data-stu-id="6562b-141">date</span></span>|<span data-ttu-id="6562b-142">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="6562b-142">DBTYPE_DBDATE</span></span>|<span data-ttu-id="6562b-143">'aaaa-mm-jj'</span><span class="sxs-lookup"><span data-stu-id="6562b-143">'yyyy-mm-dd'</span></span>|  
|<span data-ttu-id="6562b-144">time</span><span class="sxs-lookup"><span data-stu-id="6562b-144">time</span></span>|<span data-ttu-id="6562b-145">DBTYPE_DBTIME2</span><span class="sxs-lookup"><span data-stu-id="6562b-145">DBTYPE_DBTIME2</span></span>|<span data-ttu-id="6562b-146">'hh:mm:ss[.9999999]'</span><span class="sxs-lookup"><span data-stu-id="6562b-146">'hh:mm:ss[.9999999]'</span></span><br /><br /> <span data-ttu-id="6562b-147">Le cas échéant, les fractions de seconde peuvent être spécifiées à l'aide de sept chiffres au plus.</span><span class="sxs-lookup"><span data-stu-id="6562b-147">Fractional seconds can optionally be specified using up to seven digits.</span></span>|  
|<span data-ttu-id="6562b-148">datetime2</span><span class="sxs-lookup"><span data-stu-id="6562b-148">datetime2</span></span>|<span data-ttu-id="6562b-149">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="6562b-149">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="6562b-150">'aaaa-mm-jj hh:mm:ss[.fffffff]'</span><span class="sxs-lookup"><span data-stu-id="6562b-150">'yyyy-mm-dd hh:mm:ss[.fffffff]'</span></span><br /><br /> <span data-ttu-id="6562b-151">Le cas échéant, les fractions de seconde peuvent être spécifiées à l'aide de sept chiffres au plus.</span><span class="sxs-lookup"><span data-stu-id="6562b-151">Fractional seconds can optionally be specified using up to seven digits.</span></span>|  
|<span data-ttu-id="6562b-152">datetimeoffset</span><span class="sxs-lookup"><span data-stu-id="6562b-152">datetimeoffset</span></span>|<span data-ttu-id="6562b-153">DBTYPE_DBTIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="6562b-153">DBTYPE_DBTIMESTAMPOFFSET</span></span>|<span data-ttu-id="6562b-154">'aaaa-mm-jj hh:mm:ss[.fffffff] +/-hh:mm'</span><span class="sxs-lookup"><span data-stu-id="6562b-154">'yyyy-mm-dd hh:mm:ss[.fffffff] +/-hh:mm'</span></span><br /><br /> <span data-ttu-id="6562b-155">Le cas échéant, les fractions de seconde peuvent être spécifiées à l'aide de sept chiffres au plus.</span><span class="sxs-lookup"><span data-stu-id="6562b-155">Fractional seconds can optionally be specified using up to seven digits.</span></span>|  
  
 <span data-ttu-id="6562b-156">Il n'y a pas de modifications aux séquences d'échappement pour les littéraux de type date/time.</span><span class="sxs-lookup"><span data-stu-id="6562b-156">There are no changes to the escape sequences for date/time literals.</span></span>  
  
 <span data-ttu-id="6562b-157">Dans les résultats, les fractions de seconde utilisent un point (.) plutôt que les deux-points (:).</span><span class="sxs-lookup"><span data-stu-id="6562b-157">Fractional seconds in results use a dot (.) rather than a colon (:).</span></span>  
  
 <span data-ttu-id="6562b-158">Les valeurs de chaîne retournées aux applications sont toujours de la même longueur pour une colonne donnée.</span><span class="sxs-lookup"><span data-stu-id="6562b-158">String values returned to applications will always be the same length for a given column.</span></span> <span data-ttu-id="6562b-159">Les composants année, mois, jour, heure, minute et seconde seront complétés avec des zéros non significatifs pour atteindre leur largeur maximale.</span><span class="sxs-lookup"><span data-stu-id="6562b-159">Year, month, day, hour, minute, and second components will be padded with leading zeros to their maximum width.</span></span> <span data-ttu-id="6562b-160">Il y aura exactement un espace entre la date et l'heure et exactement un espace entre l'heure et le décalage horaire.</span><span class="sxs-lookup"><span data-stu-id="6562b-160">There will be exactly one space between date and time and exactly one space between the time and timezone offset.</span></span> <span data-ttu-id="6562b-161">Un décalage horaire sera toujours précédé d'un signe.</span><span class="sxs-lookup"><span data-stu-id="6562b-161">A timezone offset will always be preceded by a sign.</span></span> <span data-ttu-id="6562b-162">Ce signe est un plus (+) lorsque le décalage est nul.</span><span class="sxs-lookup"><span data-stu-id="6562b-162">This sign will be a plus (+) when the offset is zero.</span></span> <span data-ttu-id="6562b-163">Aucun espace ne figurera entre le signe et la valeur de décalage.</span><span class="sxs-lookup"><span data-stu-id="6562b-163">There will be no white space between the sign and the offset value.</span></span> <span data-ttu-id="6562b-164">Les fractions de seconde seront complétées, si nécessaire, par des zéros à droite, jusqu'à la précision définie pour la colonne, mais sans la dépasser.</span><span class="sxs-lookup"><span data-stu-id="6562b-164">Fractional seconds will be padded with trailing zeros, if necessary, up to the defined precision for the column, but no further.</span></span> <span data-ttu-id="6562b-165">Pour les colonnes datetime, il y aura trois chiffres de fractions de seconde.</span><span class="sxs-lookup"><span data-stu-id="6562b-165">For datetime columns, there will be three fractional seconds digits.</span></span> <span data-ttu-id="6562b-166">Pour les colonnes smalldatetime, il n'y aura pas de chiffres de fractions de seconde et les secondes seront toujours égales à zéro.</span><span class="sxs-lookup"><span data-stu-id="6562b-166">For smalldatetime columns, there will be no fractional seconds digits and the seconds will always be zero.</span></span>  
  
 <span data-ttu-id="6562b-167">Les conversions de valeurs de chaîne fournies par l'application seront plus flexibles et autoriseront des valeurs de composant de largeur inférieure à la largeur maximale.</span><span class="sxs-lookup"><span data-stu-id="6562b-167">Conversions from string values provided by the application will be more flexible and will allow component values less than maximum width.</span></span> <span data-ttu-id="6562b-168">Les années peuvent être de 1 à 4 chiffres.</span><span class="sxs-lookup"><span data-stu-id="6562b-168">Years can be 1-4 digits.</span></span> <span data-ttu-id="6562b-169">Les mois, les jours, les heures, les minutes et les secondes peuvent être de 1 à 2 chiffres.</span><span class="sxs-lookup"><span data-stu-id="6562b-169">Months, days, hours, minutes, and seconds can be 1 or 2 digits.</span></span> <span data-ttu-id="6562b-170">Il peut y avoir un espace arbitraire entre la date et l'heure et entre l'heure et le décalage horaire.</span><span class="sxs-lookup"><span data-stu-id="6562b-170">There can be arbitrary white space between date/time and time/timezone offsets.</span></span> <span data-ttu-id="6562b-171">Le signe d'un décalage correspondant à zéro heure et zéro minute peut être plus ou moins.</span><span class="sxs-lookup"><span data-stu-id="6562b-171">The sign of an offset with zero hours and zero minutes can be plus or minus.</span></span> <span data-ttu-id="6562b-172">Les zéros à droite sont autorisés pour les fractions de seconde avec un maximum de 9 chiffres.</span><span class="sxs-lookup"><span data-stu-id="6562b-172">Trailing zeros are allowed for fractional seconds up to a maximum of 9 digits.</span></span> <span data-ttu-id="6562b-173">Un composant heure peut se terminer avec une virgule décimale et aucun chiffre de fractions de seconde.</span><span class="sxs-lookup"><span data-stu-id="6562b-173">A time component can terminate with a decimal point and no fractional seconds digits.</span></span>  
  
 <span data-ttu-id="6562b-174">Une chaîne vide n'est pas un littéral de date et d'heure valide et ne représente pas une valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="6562b-174">An empty string is not a valid date/time literal and it does not represent a NULL value.</span></span> <span data-ttu-id="6562b-175">Une tentative de convertir une chaîne vide en valeur de date ou d'heure provoque des erreurs avec SQLState 22018 et le message « Valeur de caractère non valide pour la spécification de la casse ».</span><span class="sxs-lookup"><span data-stu-id="6562b-175">An attempt to convert an empty string to a date/time value will result in errors with SQLState 22018 and the message "Invalid character value for cast specification".</span></span>  
  
## <a name="data-formats-data-structures"></a><span data-ttu-id="6562b-176">Formats de données : structures de données</span><span class="sxs-lookup"><span data-stu-id="6562b-176">Data Formats: Data Structures</span></span>  
 <span data-ttu-id="6562b-177">Dans les structures spécifiques à OLE DB décrites ci-dessous, OLE DB se conforme aux mêmes contraintes qu'ODBC.</span><span class="sxs-lookup"><span data-stu-id="6562b-177">In the OLE DB-specific structures described below, OLE DB conforms to the same constraints as ODBC.</span></span> <span data-ttu-id="6562b-178">Celles-ci sont tirées du calendrier grégorien :</span><span class="sxs-lookup"><span data-stu-id="6562b-178">These are taken from the Gregorian calendar:</span></span>  
  
-   <span data-ttu-id="6562b-179">La plage des mois s'étend de 1 à 12.</span><span class="sxs-lookup"><span data-stu-id="6562b-179">Month range is 1 through 12.</span></span>  
  
-   <span data-ttu-id="6562b-180">La plage des jours s'étend de 1 au nombre de jours dans le mois, et doit être cohérente avec les années et les mois  en tenant compte des années bissextiles.</span><span class="sxs-lookup"><span data-stu-id="6562b-180">Day field range is 1 through the number of days in the month, and must be consistent with year and month fields, taking account of leap years.</span></span>  
  
-   <span data-ttu-id="6562b-181">La plage des heures s'étend de 0 à 23.</span><span class="sxs-lookup"><span data-stu-id="6562b-181">Hour range is 0 through 23.</span></span>  
  
-   <span data-ttu-id="6562b-182">La plage des minutes s'étend de 0 à 59.</span><span class="sxs-lookup"><span data-stu-id="6562b-182">Minute range is 0 through 59.</span></span>  
  
-   <span data-ttu-id="6562b-183">La plage des secondes s'étend de 0 à 59.</span><span class="sxs-lookup"><span data-stu-id="6562b-183">Seconds range from 0 through 59.</span></span> <span data-ttu-id="6562b-184">Ceci permet d’ajouter jusqu’à deux secondes intercalaires pour conserver la synchronisation avec l’heure sidérale.</span><span class="sxs-lookup"><span data-stu-id="6562b-184">This allows up to two leap seconds to maintain synchronization with sidereal time.</span></span>  
  
 <span data-ttu-id="6562b-185">Les implémentations pour les structs OLE DB existants suivants ont été modifiées afin de prendre en charge les nouveaux types de données de date et d'heure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6562b-185">Implementations for the following existing OLE DB structs have been modified to support the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date and time data types.</span></span> <span data-ttu-id="6562b-186">Toutefois, les définitions n'ont pas changé.</span><span class="sxs-lookup"><span data-stu-id="6562b-186">The definitions, however, have not changed.</span></span>  
  
-   <span data-ttu-id="6562b-187">DBTYPE_DATE (Ceci est un type DATE Automation.</span><span class="sxs-lookup"><span data-stu-id="6562b-187">DBTYPE_DATE (This is an automation DATE type.</span></span> <span data-ttu-id="6562b-188">Il est représenté de façon interne sous la forme d'un `double`.</span><span class="sxs-lookup"><span data-stu-id="6562b-188">It is internally represented as a `double`..</span></span> <span data-ttu-id="6562b-189">La partie entière correspond au nombre de jours depuis le 30 décembre 1899 et la partie fractionnaire correspond à la fraction d'un jour.</span><span class="sxs-lookup"><span data-stu-id="6562b-189">The whole part is the number of days since December 30, 1899 and the fractional part is the fraction of a day.</span></span> <span data-ttu-id="6562b-190">Ce type a une précision de 1 seconde et a donc une échelle effective de 0.)</span><span class="sxs-lookup"><span data-stu-id="6562b-190">This type has an accuracy of 1 second, so has an effective scale of 0.)</span></span>  
  
-   <span data-ttu-id="6562b-191">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="6562b-191">DBTYPE_DBDATE</span></span>  
  
-   <span data-ttu-id="6562b-192">DBTYPE_DBTIME</span><span class="sxs-lookup"><span data-stu-id="6562b-192">DBTYPE_DBTIME</span></span>  
  
-   <span data-ttu-id="6562b-193">DBTYPE_DBTIMESTAMP (le champ de fraction est défini par OLE DB comme le nombre de milliardièmes de seconde (nanosecondes) et il est compris entre 0 et 999 999 999)</span><span class="sxs-lookup"><span data-stu-id="6562b-193">DBTYPE_DBTIMESTAMP (the fraction field is defined by OLE DB as the number of billionths of a second (nanoseconds) and ranges from 0-999,999,999)</span></span>  
  
-   <span data-ttu-id="6562b-194">DBTYPE_FILETIME</span><span class="sxs-lookup"><span data-stu-id="6562b-194">DBTYPE_FILETIME</span></span>  
  
### <a name="dbtype_dbtime2"></a><span data-ttu-id="6562b-195">DBTYPE_DBTIME2</span><span class="sxs-lookup"><span data-stu-id="6562b-195">DBTYPE_DBTIME2</span></span>  
 <span data-ttu-id="6562b-196">Ce struct est complété jusqu'à 12 octets sur les systèmes d'exploitation 32 bits et 64 bits.</span><span class="sxs-lookup"><span data-stu-id="6562b-196">This struct is padded to 12 bytes on both 32-bit and 64-bit operating systems.</span></span>  
  
```  
typedef struct tagDBTIME2 {  
    USHORT hour;  
    USHORT minute;  
    USHORT second;  
    ULONG fraction;  
    } DBTIME2;  
```  
  
### <a name="dbtype_-dbtimestampoffset"></a><span data-ttu-id="6562b-197">DBTYPE_ DBTIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="6562b-197">DBTYPE_ DBTIMESTAMPOFFSET</span></span>  
  
```  
typedef struct tagDBTIMESTAMPOFFSET {  
    SHORT year;  
    USHORT month;  
    USHORT day;  
    USHORT hour;  
    USHORT minute;  
    USHORT second;  
    ULONG fraction;  
    SHORT timezone_hour;  
    SHORT timezone_minute;  
    } DBTIMESTAMPOFFSET;  
```  
  
 <span data-ttu-id="6562b-198">Si `timezone_hour` est négatif, `timezone_minute` doit être négatif ou égal à zéro.</span><span class="sxs-lookup"><span data-stu-id="6562b-198">If `timezone_hour` is negative, `timezone_minute` must be negative or zero.</span></span> <span data-ttu-id="6562b-199">Si `timezone_hour` est positif, `timezone minute` doit être positif ou égal à zéro.</span><span class="sxs-lookup"><span data-stu-id="6562b-199">If `timezone_hour` is positive, `timezone minute` must be positive or zero.</span></span> <span data-ttu-id="6562b-200">Si `timezone_hour` est nul, `timezone minute` peut contenir une valeur comprise entre -59 et +59.</span><span class="sxs-lookup"><span data-stu-id="6562b-200">If `timezone_hour` is zero, `timezone minute` can hold a value between -59 and +59.</span></span>  
  
### <a name="ssvariant"></a><span data-ttu-id="6562b-201">SSVARIANT</span><span class="sxs-lookup"><span data-stu-id="6562b-201">SSVARIANT</span></span>  
 <span data-ttu-id="6562b-202">Ce struct inclut désormais les nouvelles structures, DBTYPE_DBTIME2 et DBTYPE_DBTIMESTAMPOFFSET, et ajoute une échelle de fractions de seconde pour les types appropriés.</span><span class="sxs-lookup"><span data-stu-id="6562b-202">This struct now includes the new structures, DBTYPE_DBTIME2 and DBTYPE_DBTIMESTAMPOFFSET, and adds fractional seconds scale for appropriate types.</span></span>  
  
```  
struct SSVARIANT {  
   SSVARTYPE vt;  
   DWORD dwReserved1;  
   DWORD dwReserved2;  
   union {  
// ...  
      DBTIMESTAMP tsDateTimeVal;  
      DBDATE dDateVal;  
      struct _Time2Val {  
         DBTIME2 tTime2Val;  
         BYTE bScale;  
      } Time2Val;  
      struct _DateTimeVal {  
         DBTIMESTAMP tsDateTimeVal;  
         BYTE bScale;  
      } DateTimeVal;  
      struct _DateTimeOffsetVal {   
         DBTIMESTAMPOFFSET tsoDateTimeOffsetVal;  
         BYTE bScale;  
      } DateTimeOffsetVal;  
// ...  
   };  
};  
```  
  
 <span data-ttu-id="6562b-203">De plus, l'enum associé à l'encodage de type SSVARIANT, qui détermine le type de l'enum sera étendu comme suit :</span><span class="sxs-lookup"><span data-stu-id="6562b-203">In addition, the enum associated with SSVARIANT type encoding, which determines the type of the enum, will be extended as follows:</span></span>  
  
```  
enum SQLVARENUM {  
// ...  
   // Datetime  
   VT_SS_DATETIME      = DBTYPE_DBTIMESTAMP,  
   VT_SS_SMALLDATETIME = 206,  
  
   VT_SS_DATE = DBTYPE_DBDATE,  
   VT_SS_TIME2 = DBTYPE_DBTIME2,  
   VT_SS_DATETIME2 = 212  
   VT_SS_DATETIMEOFFSET = DBTYPE_DBTIMESTAMPOFFSET  
};  
```  
  
 <span data-ttu-id="6562b-204">Les applications migrant vers [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client qui utilisent `sql_variant` et s'appuient sur la précision limitée de `datetime` devront être mis à jour si le schéma sous-jacent est mis à jour pour utiliser `datetime2` plutôt que `datetime`.</span><span class="sxs-lookup"><span data-stu-id="6562b-204">Applications migrating to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client that use `sql_variant` and rely on the limited precision of `datetime` will have to be updated if the underlying schema is updated to use `datetime2` rather than `datetime`.</span></span>  
  
 <span data-ttu-id="6562b-205">Les macros d'accès pour SSVARIANT ont également été étendues avec l'addition des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="6562b-205">The access macros for SSVARIANT have also been extended with the addition of the following:</span></span>  
  
```  
#define V_SS_DATETIME2(X)       V_SS_UNION(X, DateTimeVal)  
#define V_SS_TIME2(X)           V_SS_UNION(X, Time2Val)  
#define V_SS_DATE(X)            V_SS_UNION(X, dDateVal)  
#define V_SS_DATETIMEOFFSET(X)  V_SS_UNION(X, DateTimeOffsetVal)  
```  
  
## <a name="data-type-mapping-in-itabledefinitioncreatetable"></a><span data-ttu-id="6562b-206">Mappage des types de données dans ITableDefinition::CreateTable</span><span class="sxs-lookup"><span data-stu-id="6562b-206">Data Type Mapping in ITableDefinition::CreateTable</span></span>  
 <span data-ttu-id="6562b-207">Le mappage de type suivant est utilisé avec les structures DBCOLUMNDESC utilisées par ITableDefinition::CreateTable :</span><span class="sxs-lookup"><span data-stu-id="6562b-207">The following type mapping is used with DBCOLUMNDESC structures used by ITableDefinition::CreateTable:</span></span>  
  
|<span data-ttu-id="6562b-208">Type de données OLE DB (*wType*)</span><span class="sxs-lookup"><span data-stu-id="6562b-208">OLE DB data type (*wType*)</span></span>|<span data-ttu-id="6562b-209">Type de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6562b-209">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type</span></span>|<span data-ttu-id="6562b-210">Notes</span><span class="sxs-lookup"><span data-stu-id="6562b-210">Notes</span></span>|  
|----------------------------------|-----------------------------------------|-----------|  
|<span data-ttu-id="6562b-211">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="6562b-211">DBTYPE_DBDATE</span></span>|<span data-ttu-id="6562b-212">Date</span><span class="sxs-lookup"><span data-stu-id="6562b-212">date</span></span>||  
|<span data-ttu-id="6562b-213">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="6562b-213">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="6562b-214">`datetime2`(p)</span><span class="sxs-lookup"><span data-stu-id="6562b-214">`datetime2`(p)</span></span>|<span data-ttu-id="6562b-215">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client inspecte le membre *bScale* DBCOLUMDESC pour déterminer la précision en fractions de seconde.</span><span class="sxs-lookup"><span data-stu-id="6562b-215">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider inspects the DBCOLUMDESC *bScale* member to determine the fractional seconds precision.</span></span>|  
|<span data-ttu-id="6562b-216">DBTYPE_DBTIME2</span><span class="sxs-lookup"><span data-stu-id="6562b-216">DBTYPE_DBTIME2</span></span>|<span data-ttu-id="6562b-217">`time`(p)</span><span class="sxs-lookup"><span data-stu-id="6562b-217">`time`(p)</span></span>|<span data-ttu-id="6562b-218">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client inspecte le membre *bScale* DBCOLUMDESC pour déterminer la précision en fractions de seconde.</span><span class="sxs-lookup"><span data-stu-id="6562b-218">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider inspects the DBCOLUMDESC *bScale* member to determine the fractional seconds precision.</span></span>|  
|<span data-ttu-id="6562b-219">DBTYPE_DBTIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="6562b-219">DBTYPE_DBTIMESTAMPOFFSET</span></span>|<span data-ttu-id="6562b-220">`datetimeoffset`(p)</span><span class="sxs-lookup"><span data-stu-id="6562b-220">`datetimeoffset`(p)</span></span>|<span data-ttu-id="6562b-221">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client inspecte le membre *bScale* DBCOLUMDESC pour déterminer la précision en fractions de seconde.</span><span class="sxs-lookup"><span data-stu-id="6562b-221">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider inspects the DBCOLUMDESC *bScale* member to determine the fractional seconds precision.</span></span>|  
  
 <span data-ttu-id="6562b-222">Lorsqu’une application spécifie DBTYPE_DBTIMESTAMP dans *wType*, elle peut remplacer le mappage en `datetime2` en fournissant un nom de type dans *pwszTypeName*.</span><span class="sxs-lookup"><span data-stu-id="6562b-222">When an application specifies DBTYPE_DBTIMESTAMP in *wType*, it can override the mapping to `datetime2` by supplying a type name in *pwszTypeName*.</span></span> <span data-ttu-id="6562b-223">Si `datetime` est spécifié, *bScale* doit avoir la 3.</span><span class="sxs-lookup"><span data-stu-id="6562b-223">If `datetime` is specified, *bScale* must be 3.</span></span> <span data-ttu-id="6562b-224">Si `smalldatetime` est spécifié, *bScale* doit avoir la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="6562b-224">If `smalldatetime` is specified, *bScale* must be 0.</span></span> <span data-ttu-id="6562b-225">Si *bScale* n’est pas cohérent avec *wType* et *pwszTypeName*, DB_E_BADSCALE est retourné.</span><span class="sxs-lookup"><span data-stu-id="6562b-225">If *bScale* is not consistent with *wType* and *pwszTypeName*,DB_E_BADSCALE is returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6562b-226">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6562b-226">See Also</span></span>  
 [<span data-ttu-id="6562b-227">Améliorations des types de données de date et d’heure &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="6562b-227">Date and Time Improvements &#40;OLE DB&#41;</span></span>](date-and-time-improvements-ole-db.md)  
  
  
