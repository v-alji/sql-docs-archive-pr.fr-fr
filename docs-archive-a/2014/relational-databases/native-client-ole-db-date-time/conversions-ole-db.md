---
title: Liaisons et conversions (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- conversions [OLE DB]
- bindings [OLE DB]
- OLE DB, bindings and conversions
ms.assetid: c187df58-a8c8-4c74-a76f-663abbc5f0c1
author: rothja
ms.author: jroth
ms.openlocfilehash: 95c73bdad80b5f948a45235ad208ab307fcceff3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613460"
---
# <a name="bindings-and-conversions-ole-db"></a><span data-ttu-id="7eb3e-102">Liaisons et conversions (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="7eb3e-102">Bindings and Conversions (OLE DB)</span></span>
  <span data-ttu-id="7eb3e-103">Cette section explique comment réaliser des conversions entre des valeurs `datetime` et `datetimeoffset`.</span><span class="sxs-lookup"><span data-stu-id="7eb3e-103">This section discusses how to convert between `datetime` and `datetimeoffset` values.</span></span> <span data-ttu-id="7eb3e-104">Les conversions décrites dans cette section sont soit déjà fournies par OLE DB, soit une extension cohérente de ce dernier.</span><span class="sxs-lookup"><span data-stu-id="7eb3e-104">The conversions described in this section are either already provided by OLE DB or are a consistent extension of OLE DB.</span></span>  
  
 <span data-ttu-id="7eb3e-105">Le format des littéraux et des chaînes pour les dates et les heures dans OLE DB suit généralement la norme ISO et ne dépend pas des paramètres régionaux du client.</span><span class="sxs-lookup"><span data-stu-id="7eb3e-105">The format of literals and strings for dates and times in OLE DB generally follows ISO, and is not dependent on the client locale.</span></span> <span data-ttu-id="7eb3e-106">Une exception est DBTYPE_DATE où la norme est OLE Automation.</span><span class="sxs-lookup"><span data-stu-id="7eb3e-106">One exception is DBTYPE_DATE, where the standard is OLE Automation.</span></span> <span data-ttu-id="7eb3e-107">Toutefois, du fait que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client effectue uniquement des conversions entre des types lorsque des données sont transmises vers ou depuis le client, il n'existe aucun moyen de contraindre [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client à effectuer des conversions entre DBTYPE_DATE et un format de chaîne.</span><span class="sxs-lookup"><span data-stu-id="7eb3e-107">However, because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client only converts between types when data is transmitted to or from the client, there is no way for an application to force [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client to convert between DBTYPE_DATE and string formats.</span></span> <span data-ttu-id="7eb3e-108">Sinon, les chaînes utilisent les formats suivants (le texte entre crochets indique un élément facultatif) :</span><span class="sxs-lookup"><span data-stu-id="7eb3e-108">Otherwise, strings use the following formats (text in brackets indicates an optional element):</span></span>  
  
-   <span data-ttu-id="7eb3e-109">Le format des chaînes `datetime` et `datetimeoffset` est le suivant :</span><span class="sxs-lookup"><span data-stu-id="7eb3e-109">The format of `datetime` and `datetimeoffset` strings is:</span></span>  
  
     <span data-ttu-id="7eb3e-110">*aaaa* - *mm* - *JJ*[ *hh*:*mm*:*SS*[.\* 9999999\*] [ ??</span><span class="sxs-lookup"><span data-stu-id="7eb3e-110">*yyyy*-*mm*-*dd*[ *hh*:*mm*:*ss*[.*9999999*][ ??</span></span> <span data-ttu-id="7eb3e-111">*hh*:*mm*]]</span><span class="sxs-lookup"><span data-stu-id="7eb3e-111">*hh*:*mm*]]</span></span>  
  
-   <span data-ttu-id="7eb3e-112">Le format des chaînes `time` est le suivant :</span><span class="sxs-lookup"><span data-stu-id="7eb3e-112">The format of `time` strings is:</span></span>  
  
     <span data-ttu-id="7eb3e-113">*hh*:*mm*:*ss*[.*9999999*]</span><span class="sxs-lookup"><span data-stu-id="7eb3e-113">*hh*:*mm*:*ss*[.*9999999*]</span></span>  
  
-   <span data-ttu-id="7eb3e-114">Le format des chaînes `date` est le suivant :</span><span class="sxs-lookup"><span data-stu-id="7eb3e-114">The format of `date` strings is:</span></span>  
  
     <span data-ttu-id="7eb3e-115">*aaaa*-*mm*-*jj*</span><span class="sxs-lookup"><span data-stu-id="7eb3e-115">*yyyy*-*mm*-*dd*</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7eb3e-116">Les versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client et SQLOLEDB autorisaient l'implémentation de conversions OLE en cas d'échec des processus de conversion standard.</span><span class="sxs-lookup"><span data-stu-id="7eb3e-116">Earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client and SQLOLEDB implemented OLE conversions, in case standard conversions failed.</span></span> <span data-ttu-id="7eb3e-117">C'est pourquoi certaines conversions réalisées par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 10.0 et versions ultérieures diffèrent de la spécification OLE DB.</span><span class="sxs-lookup"><span data-stu-id="7eb3e-117">As a result, some conversions performed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 10.0 and later differ from the OLE DB specification.</span></span>  
  
 <span data-ttu-id="7eb3e-118">Les conversions de chaînes autorisent une souplesse en matière d'espace et de largeur de champ.</span><span class="sxs-lookup"><span data-stu-id="7eb3e-118">Conversions from strings allow flexibility in white space and field width.</span></span> <span data-ttu-id="7eb3e-119">Pour plus d’informations, consultez la section « formats de données : chaînes et littéraux » dans [type de données prise en charge de OLE DB améliorations de la date et](data-type-support-for-ole-db-date-and-time-improvements.md)de l’heure.</span><span class="sxs-lookup"><span data-stu-id="7eb3e-119">For more information, see the "Data Formats: Strings and Literals" section in [Data Type Support for OLE DB Date and Time Improvements](data-type-support-for-ole-db-date-and-time-improvements.md).</span></span>  
  
 <span data-ttu-id="7eb3e-120">Les règles suivantes sont les règles générales de conversion :</span><span class="sxs-lookup"><span data-stu-id="7eb3e-120">The following are general conversion rules:</span></span>  
  
-   <span data-ttu-id="7eb3e-121">Lorsqu'une chaîne est convertie en type date/heure, la chaîne est d'abord analysée en tant que littéral ISO.</span><span class="sxs-lookup"><span data-stu-id="7eb3e-121">When a string is converted to a date/time type, the string is first parsed as an ISO literal.</span></span> <span data-ttu-id="7eb3e-122">En cas d'échec, la chaîne est analysée comme un littéral de date OLE doté de composants heure.</span><span class="sxs-lookup"><span data-stu-id="7eb3e-122">If this fails, the string is parsed as an OLE date literal, which has time components.</span></span>  
  
-   <span data-ttu-id="7eb3e-123">Si aucune heure n'est fournie mais le récepteur peut stocker l'heure, l'heure est définie avec la valeur zéro.</span><span class="sxs-lookup"><span data-stu-id="7eb3e-123">If no time is present but the receiver can store time, the time is set to zero.</span></span> <span data-ttu-id="7eb3e-124">Si aucune date n'est fournie mais le récepteur peut stocker une date, la date définie est la date actuelle qui utilise les conversions ISO ou bien 1899-12-30 qui utilise les conversions OLE.</span><span class="sxs-lookup"><span data-stu-id="7eb3e-124">If no date is present but the receiver can store a date, the date is set to the current date when ISO conversions are used and to 1899-12-30 when OLE conversions are used.</span></span>  
  
-   <span data-ttu-id="7eb3e-125">Si aucun fuseau horaire n'est fourni dans le type de données que le client utilise mais si le serveur peut stocker le fuseau, les données du client sont supposées apparaître dans le fuseau horaire du client.</span><span class="sxs-lookup"><span data-stu-id="7eb3e-125">If no timezone is present in the data type that the client is using, but the server can store timezone, the data on the client is assumed to be in the client timezone.</span></span>  
  
-   <span data-ttu-id="7eb3e-126">Si aucun fuseau horaire n'est fourni au serveur mais le client dispose d'informations sur les fuseaux, le fuseau horaire UTC est adopté.</span><span class="sxs-lookup"><span data-stu-id="7eb3e-126">If no timezone is present at the server but the client has timezone information, the UTC timezone is assumed.</span></span> <span data-ttu-id="7eb3e-127">Ce comportement diffère de celui du serveur.</span><span class="sxs-lookup"><span data-stu-id="7eb3e-127">This differs from server behavior.</span></span>  
  
-   <span data-ttu-id="7eb3e-128">Si l'heure est fournie mais le récepteur ne peut pas la stocker, le composant heure est ignoré.</span><span class="sxs-lookup"><span data-stu-id="7eb3e-128">If the time is present but the receiver cannot store time, the time component is ignored.</span></span>  
  
-   <span data-ttu-id="7eb3e-129">Si la date est fournie mais le récepteur ne peut pas la stocker, le composant date est ignoré.</span><span class="sxs-lookup"><span data-stu-id="7eb3e-129">If the date is present but the receiver cannot store the date, the date component is ignored.</span></span>  
  
-   <span data-ttu-id="7eb3e-130">En cas de troncation des secondes ou des fractions de seconde lors de la conversion du client au serveur, DB_E_ERRORSOCCURRED est retourné et l'état DBSTATUS_E_DATAOVERFLOW est défini.</span><span class="sxs-lookup"><span data-stu-id="7eb3e-130">If truncation of seconds or fractional seconds occurs when converting from client to server, DB_E_ERRORSOCCURRED is returned and the status DBSTATUS_E_DATAOVERFLOW is set.</span></span>  
  
-   <span data-ttu-id="7eb3e-131">En cas de troncation des secondes ou des fractions de seconde lors de la conversion du serveur au client, DBSTATUS_S_TRUNCATED est défini</span><span class="sxs-lookup"><span data-stu-id="7eb3e-131">If truncation of seconds or fractional seconds occurs when converting from server to client, DBSTATUS_S_TRUNCATED is set</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7eb3e-132">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="7eb3e-132">In This Section</span></span>  
 [<span data-ttu-id="7eb3e-133">Conversions de client à serveur</span><span class="sxs-lookup"><span data-stu-id="7eb3e-133">Conversions Performed from Client to Server</span></span>](conversions-performed-from-client-to-server.md)  
 <span data-ttu-id="7eb3e-134">Décrit les conversions date/heure effectuées entre une application cliente écrite avec le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client et [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (ou version ultérieure).</span><span class="sxs-lookup"><span data-stu-id="7eb3e-134">Describes date/time conversions performed between a client application written with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (or later).</span></span>  
  
 [<span data-ttu-id="7eb3e-135">Conversions de serveur à client</span><span class="sxs-lookup"><span data-stu-id="7eb3e-135">Conversions Performed from Server to Client</span></span>](conversions-performed-from-server-to-client.md)  
 <span data-ttu-id="7eb3e-136">Décrit les conversions date/heure effectuées entre [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (ou version ultérieure) et une application cliente écrite avec le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="7eb3e-136">Describes date/time conversions performed between [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (or later) and a client application written with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eb3e-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7eb3e-137">See Also</span></span>  
 [<span data-ttu-id="7eb3e-138">Améliorations des types de données de date et d’heure &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="7eb3e-138">Date and Time Improvements &#40;OLE DB&#41;</span></span>](date-and-time-improvements-ole-db.md)  
  
  
