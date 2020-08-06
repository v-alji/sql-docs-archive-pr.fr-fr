---
title: Encoder et décoder des identificateurs SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: bb9fe0d3-e432-42d3-b324-64dc908b544a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 88e7ebbc81d9c3cb91b1bf678075c5b5d0884890
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696908"
---
# <a name="encode-and-decode-sql-server-identifiers"></a><span data-ttu-id="ad2cf-102">Encoder et décoder des identificateurs SQL Server</span><span class="sxs-lookup"><span data-stu-id="ad2cf-102">Encode and Decode SQL Server Identifiers</span></span>
  <span data-ttu-id="ad2cf-103">Les identificateurs délimités SQL Server contiennent parfois des caractères non pris en charge dans les chemins d'accès Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ad2cf-103">SQL Server delimited identifiers sometimes contain characters not supported in Windows PowerShell paths.</span></span> <span data-ttu-id="ad2cf-104">Vous pouvez spécifier ces caractères en encodant leurs valeurs hexadécimales.</span><span class="sxs-lookup"><span data-stu-id="ad2cf-104">These characters can be specified by encoding their hexadecimal values.</span></span>  
  
1.  <span data-ttu-id="ad2cf-105">**Avant de commencer :**  [Limitations et restrictions](#LimitationsRestrictions)</span><span class="sxs-lookup"><span data-stu-id="ad2cf-105">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions)</span></span>  
  
2.  <span data-ttu-id="ad2cf-106">**Pour traiter des caractères spéciaux :**  [Encodage d'un identificateur](#EncodeIdent), [Décodage d'un identificateur](#DecodeIdent)</span><span class="sxs-lookup"><span data-stu-id="ad2cf-106">**To process special characters:**  [Encoding an Identifier](#EncodeIdent), [Decoding an Identifier](#DecodeIdent)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="ad2cf-107">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="ad2cf-107">Before You Begin</span></span>  
 <span data-ttu-id="ad2cf-108">Les caractères qui ne sont pas pris en charge dans les noms de chemins d’accès Windows PowerShell peuvent être représentés, ou encodés, sous la forme du caractère « % » suivi de la valeur hexadécimale pour le modèle binaire qui représente le caractère, comme dans « **%** XX ».</span><span class="sxs-lookup"><span data-stu-id="ad2cf-108">Characters that are not supported in Windows PowerShell path names can be represented, or encoded, as the "%" character followed by the hexadecimal value for the bit pattern that represents the character, as in "**%** xx".</span></span> <span data-ttu-id="ad2cf-109">Le codage peut toujours être utilisé pour gérer des caractères qui ne sont pas pris en charge dans les chemins d'accès Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ad2cf-109">Encoding can always be used to handle characters that are not supported in Windows PowerShell paths.</span></span>  
  
 <span data-ttu-id="ad2cf-110">L’applet de commande **Encode-SqlName** prend comme entrée un identificateur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ad2cf-110">The **Encode-SqlName** cmdlet takes as input a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifier.</span></span> <span data-ttu-id="ad2cf-111">Elle génère une chaîne contenant tous les caractères qui ne sont pas pris en charge par le langage Windows PowerShell codés avec « % xx ».</span><span class="sxs-lookup"><span data-stu-id="ad2cf-111">It outputs a string with all the characters that are not supported by the Windows PowerShell language encoded with "%xx".</span></span> <span data-ttu-id="ad2cf-112">L’applet de commande **Decode-SqlName** prend comme entrée un identificateur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] encodé et retourne l’identificateur d’origine.</span><span class="sxs-lookup"><span data-stu-id="ad2cf-112">The **Decode-SqlName** cmdlet takes as input an encoded [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifier and returns the original identifier.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="ad2cf-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="ad2cf-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="ad2cf-114">Les applets de commande `Encode-Sqlname` et `Decode-Sqlname` encodent ou décodent uniquement les caractères autorisés dans les identificateurs délimités SQL Server, mais ne sont pas prises en charge dans les chemins d'accès PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ad2cf-114">The `Encode-Sqlname` and `Decode-Sqlname` cmdlets only encode or decode the characters that are allowed in SQL Server delimited identifiers, but are not supported in PowerShell paths.</span></span> <span data-ttu-id="ad2cf-115">Voici les caractères encodés par **Encode-SqlName** et décodés par **Decode-SqlName**:</span><span class="sxs-lookup"><span data-stu-id="ad2cf-115">These are the characters encoded by **Encode-SqlName** and decoded by **Decode-SqlName**:</span></span>  
  
|||||||||||||  
|-|-|-|-|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="ad2cf-116">**Caractère**</span><span class="sxs-lookup"><span data-stu-id="ad2cf-116">**Character**</span></span>|\ |/|<span data-ttu-id="ad2cf-117">:</span><span class="sxs-lookup"><span data-stu-id="ad2cf-117">:</span></span>|%|\<|>|*|<span data-ttu-id="ad2cf-118">?</span><span class="sxs-lookup"><span data-stu-id="ad2cf-118">?</span></span>|<span data-ttu-id="ad2cf-119">[</span><span class="sxs-lookup"><span data-stu-id="ad2cf-119">[</span></span>|<span data-ttu-id="ad2cf-120">]</span><span class="sxs-lookup"><span data-stu-id="ad2cf-120">]</span></span>|<span data-ttu-id="ad2cf-121">&#124;</span><span class="sxs-lookup"><span data-stu-id="ad2cf-121">&#124;</span></span>|  
|<span data-ttu-id="ad2cf-122">**Encodage hexadécimal**</span><span class="sxs-lookup"><span data-stu-id="ad2cf-122">**Hexadecimal Encoding**</span></span>|<span data-ttu-id="ad2cf-123">%5C</span><span class="sxs-lookup"><span data-stu-id="ad2cf-123">%5C</span></span>|<span data-ttu-id="ad2cf-124">%2F</span><span class="sxs-lookup"><span data-stu-id="ad2cf-124">%2F</span></span>|<span data-ttu-id="ad2cf-125">%3A</span><span class="sxs-lookup"><span data-stu-id="ad2cf-125">%3A</span></span>|<span data-ttu-id="ad2cf-126">%25</span><span class="sxs-lookup"><span data-stu-id="ad2cf-126">%25</span></span>|<span data-ttu-id="ad2cf-127">%3C</span><span class="sxs-lookup"><span data-stu-id="ad2cf-127">%3C</span></span>|<span data-ttu-id="ad2cf-128">%3E</span><span class="sxs-lookup"><span data-stu-id="ad2cf-128">%3E</span></span>|<span data-ttu-id="ad2cf-129">%2A</span><span class="sxs-lookup"><span data-stu-id="ad2cf-129">%2A</span></span>|<span data-ttu-id="ad2cf-130">%3F</span><span class="sxs-lookup"><span data-stu-id="ad2cf-130">%3F</span></span>|<span data-ttu-id="ad2cf-131">%5B</span><span class="sxs-lookup"><span data-stu-id="ad2cf-131">%5B</span></span>|<span data-ttu-id="ad2cf-132">%5D</span><span class="sxs-lookup"><span data-stu-id="ad2cf-132">%5D</span></span>|<span data-ttu-id="ad2cf-133">%7C</span><span class="sxs-lookup"><span data-stu-id="ad2cf-133">%7C</span></span>|  
  
##  <a name="encoding-an-identifier"></a><a name="EncodeIdent"></a><span data-ttu-id="ad2cf-134">Encodage d’un identificateur</span><span class="sxs-lookup"><span data-stu-id="ad2cf-134">Encoding an Identifier</span></span>  
 <span data-ttu-id="ad2cf-135">**Pour encoder un identificateur SQL Server dans un chemin d'accès PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ad2cf-135">**To encode a SQL Server identifier in a PowerShell path**</span></span>  
  
-   <span data-ttu-id="ad2cf-136">Utilisez l'une des deux méthodes suivantes pour encoder un identificateur SQL Server :</span><span class="sxs-lookup"><span data-stu-id="ad2cf-136">Use one of two methods to encode a SQL Server identifier:</span></span>  
  
    -   <span data-ttu-id="ad2cf-137">Spécifiez le code hexadécimal du caractère non pris en charge à l'aide de la syntaxe %XX, où XX est le code hexadécimal.</span><span class="sxs-lookup"><span data-stu-id="ad2cf-137">Specify the hexadecimal code for the unsupported character using the syntax %XX, where XX is the hexadecimal code.</span></span>  
  
    -   <span data-ttu-id="ad2cf-138">Passez l'identificateur en tant que chaîne entre guillemets à l'applet de commande `Encode-Sqlname`</span><span class="sxs-lookup"><span data-stu-id="ad2cf-138">Pass the identifier as a quoted string to the `Encode-Sqlname` cmdlet</span></span>  
  
### <a name="examples-encoding"></a><span data-ttu-id="ad2cf-139">Exemples (encodage)</span><span class="sxs-lookup"><span data-stu-id="ad2cf-139">Examples (Encoding)</span></span>  
 <span data-ttu-id="ad2cf-140">Cet exemple spécifie la version encodée du caractère « : » (%3A) :</span><span class="sxs-lookup"><span data-stu-id="ad2cf-140">This example specifies the encoded version of the ":" character (%3A):</span></span>  
  
```  
Set-Location Table%3ATest  
```  
  
 <span data-ttu-id="ad2cf-141">Vous pouvez également utiliser **Encode-SqlName** pour générer un nom pris en charge par Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="ad2cf-141">Alternatively, you can use **Encode-SqlName** to build a name supported by Windows PowerShell:</span></span>  
  
```powershell
Set-Location (Encode-SqlName "Table:Test")  
```  
  
##  <a name="decoding-an-identifier"></a><a name="DecodeIdent"></a><span data-ttu-id="ad2cf-142">Décodage d’un identificateur</span><span class="sxs-lookup"><span data-stu-id="ad2cf-142">Decoding an Identifier</span></span>  
 <span data-ttu-id="ad2cf-143">**Pour décoder un identificateur SQL Server à partir d'un chemin d'accès PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ad2cf-143">**To decode a SQL Server identifier from a PowerShell path**</span></span>  
  
 <span data-ttu-id="ad2cf-144">Utilisez l'applet de commande `Decode-Sqlname` pour remplacer les encodages hexadécimaux par les caractères représentés par l'encodage.</span><span class="sxs-lookup"><span data-stu-id="ad2cf-144">Use the `Decode-Sqlname` cmdlet to replace the hexadecimal encodings with the characters represented by the encoding.</span></span>  
  
### <a name="examples-decoding"></a><span data-ttu-id="ad2cf-145">Exemples (décodage)</span><span class="sxs-lookup"><span data-stu-id="ad2cf-145">Examples (Decoding)</span></span>  
 <span data-ttu-id="ad2cf-146">Cet exemple retourne « Table:Test » :</span><span class="sxs-lookup"><span data-stu-id="ad2cf-146">This example returns "Table:Test":</span></span>  
  
```powershell
Decode-SqlName "Table%3ATest"  
```  
  
## <a name="see-also"></a><span data-ttu-id="ad2cf-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ad2cf-147">See Also</span></span>  
 <span data-ttu-id="ad2cf-148">[Identificateurs de SQL Server dans PowerShell](sql-server-identifiers-in-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="ad2cf-148">[SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md) </span></span>  
 <span data-ttu-id="ad2cf-149">[Fournisseur SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="ad2cf-149">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="ad2cf-150">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad2cf-150">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
