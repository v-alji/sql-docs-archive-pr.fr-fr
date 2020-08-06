---
title: Syntaxe de la commande | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, commands
- commands [OLE DB]
- SQL Server Native Client OLE DB provider, stored procedures
- stored procedures [OLE DB], command syntax
ms.assetid: d463d3d7-e5cb-426d-8e92-aa29980356b6
author: rothja
ms.author: jroth
ms.openlocfilehash: da5ddb75a5c6fc10db031707b7d97ead71363e9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709268"
---
# <a name="command-syntax"></a><span data-ttu-id="ccfe2-102">Syntaxe de la commande</span><span class="sxs-lookup"><span data-stu-id="ccfe2-102">Command Syntax</span></span>
  <span data-ttu-id="ccfe2-103">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client reconnaît la syntaxe de commande spécifiée par la macro DBGUID_SQL.</span><span class="sxs-lookup"><span data-stu-id="ccfe2-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider recognizes command syntax specified by the DBGUID_SQL macro.</span></span> <span data-ttu-id="ccfe2-104">Pour le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client, le spécificateur indique qu’un amalgame de ODBC SQL, ISO et [!INCLUDE[tsql](../../includes/tsql-md.md)] est une syntaxe valide.</span><span class="sxs-lookup"><span data-stu-id="ccfe2-104">For the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the specifier indicates that an amalgam of ODBC SQL, ISO, and [!INCLUDE[tsql](../../includes/tsql-md.md)] is valid syntax.</span></span> <span data-ttu-id="ccfe2-105">Par exemple, l'instruction SQL suivante utilise une séquence d'échappement ODBC SQL pour spécifier la fonction de chaîne LCASE :</span><span class="sxs-lookup"><span data-stu-id="ccfe2-105">For example, the following SQL statement uses an ODBC SQL escape sequence to specify the LCASE string function:</span></span>  
  
```  
SELECT customerid={fn LCASE(CustomerID)} FROM Customers  
```  
  
 <span data-ttu-id="ccfe2-106">LCASE retourne une chaîne de caractères, en convertissant toutes les majuscules en leurs équivalents minuscules.</span><span class="sxs-lookup"><span data-stu-id="ccfe2-106">LCASE returns a character string, converting all uppercase characters to their lowercase equivalents.</span></span> <span data-ttu-id="ccfe2-107">La fonction de chaîne ISO LOWER effectue la même opération, si bien que l'instruction SQL suivante correspond à l'équivalent ISO de l'instruction ODBC présentée ci-dessus :</span><span class="sxs-lookup"><span data-stu-id="ccfe2-107">The ISO string function LOWER performs the same operation, so the following SQL statement is a ISO equivalent to the ODBC statement presented above:</span></span>  
  
```  
SELECT customerid=LOWER(CustomerID) FROM Customers  
```  
  
 <span data-ttu-id="ccfe2-108">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client traite les deux formes de l’instruction avec succès lorsqu’il est spécifié sous forme de texte pour une commande.</span><span class="sxs-lookup"><span data-stu-id="ccfe2-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider processes either form of the statement successfully when specified as text for a command.</span></span>  
  
## <a name="stored-procedures"></a><span data-ttu-id="ccfe2-109">Procédures stockées</span><span class="sxs-lookup"><span data-stu-id="ccfe2-109">Stored Procedures</span></span>  
 <span data-ttu-id="ccfe2-110">Lors de l’exécution d’une [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] procédure stockée à l’aide d’une [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] commande du fournisseur OLE DB Native Client, utilisez la séquence d’échappement ODBC Call dans le texte de la commande.</span><span class="sxs-lookup"><span data-stu-id="ccfe2-110">When executing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedure using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider command, use the ODBC CALL escape sequence in the command text.</span></span> <span data-ttu-id="ccfe2-111">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client utilise ensuite le mécanisme d’appel de procédure distante de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour optimiser le traitement des commandes.</span><span class="sxs-lookup"><span data-stu-id="ccfe2-111">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider then uses the remote procedure call mechanism of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to optimize command processing.</span></span> <span data-ttu-id="ccfe2-112">Par exemple, l'instruction ODBC SQL suivante correspond à un texte de commande préféré par rapport à la forme [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="ccfe2-112">For example, the following ODBC SQL statement is preferred command text over the [!INCLUDE[tsql](../../includes/tsql-md.md)] form:</span></span>  
  
-   <span data-ttu-id="ccfe2-113">ODBC SQL</span><span class="sxs-lookup"><span data-stu-id="ccfe2-113">ODBC SQL</span></span>  
  
    ```  
    {call SalesByCategory('Produce', '1995')}  
    ```  
  
-   <span data-ttu-id="ccfe2-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ccfe2-114">Transact-SQL</span></span>  
  
    ```  
    EXECUTE SalesByCategory 'Produce', '1995'  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ccfe2-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ccfe2-115">See Also</span></span>  
 [<span data-ttu-id="ccfe2-116">Commandes</span><span class="sxs-lookup"><span data-stu-id="ccfe2-116">Commands</span></span>](commands.md)  
  
  
