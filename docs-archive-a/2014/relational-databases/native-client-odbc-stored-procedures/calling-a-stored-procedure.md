---
title: Appel d’une procédure stockée | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- calling stored procedures
- ODBC, stored procedures
- stored procedures [ODBC], calling
- SQL Server Native Client ODBC driver, stored procedures
- ODBC CALL escape sequence
- escape sequences [SQL Server]
- CALL statement
ms.assetid: d13737f4-f641-45bf-b56c-523e2ffc080f
author: rothja
ms.author: jroth
ms.openlocfilehash: c6fa704e45e4e85b479ae8a40a3e567bea1ec5e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709319"
---
# <a name="calling-a-stored-procedure"></a><span data-ttu-id="4aefb-102">Appel d'une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="4aefb-102">Calling a Stored Procedure</span></span>
  <span data-ttu-id="4aefb-103">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client prend en charge à la fois la séquence d’échappement ODBC Call et l' [!INCLUDE[tsql](../../includes/tsql-md.md)] instruction [Execute](/sql/t-sql/language-elements/execute-transact-sql) pour exécuter des procédures stockées ; la séquence d’échappement ODBC Call est la méthode recommandée.</span><span class="sxs-lookup"><span data-stu-id="4aefb-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports both the ODBC CALL escape sequence and the [!INCLUDE[tsql](../../includes/tsql-md.md)][EXECUTE](/sql/t-sql/language-elements/execute-transact-sql) statement for executing stored procedures; the ODBC CALL escape sequence is the preferred method.</span></span> <span data-ttu-id="4aefb-104">L'utilisation de la syntaxe ODBC permet à une application de récupérer les codes de retour de procédures stockées et le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client est également optimisé pour utiliser un protocole initialement développé pour envoyer des appels de procédure distante (RPC) entre des ordinateurs qui exécutent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4aefb-104">Using ODBC syntax enables an application to retrieve the return codes of stored procedures and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver is also optimized to use a protocol originally developed for sending remote procedure (RPC) calls between computers running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4aefb-105">Ce protocole RPC augmente les performances en supprimant une bonne partie du traitement des paramètres et de l'analyse des instructions sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="4aefb-105">This RPC protocol increases performance by eliminating much of the parameter processing and statement parsing done on the server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4aefb-106">Lors [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de l’appel de procédures stockées à l’aide de paramètres nommés avec ODBC (pour plus d’informations, consultez [liaison de paramètres par nom (paramètres nommés)](https://go.microsoft.com/fwlink/?LinkID=209721)), les noms de paramètres doivent commencer par le \@ caractère «».</span><span class="sxs-lookup"><span data-stu-id="4aefb-106">When calling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures using named parameters with ODBC (for more information, see [Binding Parameters by Name (Named Parameters)](https://go.microsoft.com/fwlink/?LinkID=209721)), the parameter names must start with the '\@' character.</span></span> <span data-ttu-id="4aefb-107">Il s'agit d'une restriction spécifique à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4aefb-107">This is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] specific restriction.</span></span> <span data-ttu-id="4aefb-108">Le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client applique cette restriction plus strictement que MDAC (Microsoft Data Access Components).</span><span class="sxs-lookup"><span data-stu-id="4aefb-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver enforces this restriction more strictly than the Microsoft Data Access Components (MDAC).</span></span>  
  
 <span data-ttu-id="4aefb-109">La séquence d'échappement ODBC CALL permettant d'appeler une procédure est la suivante :</span><span class="sxs-lookup"><span data-stu-id="4aefb-109">The ODBC CALL escape sequence for calling a procedure is:</span></span>  
  
 <span data-ttu-id="4aefb-110">{[**? =**]**appel**_PROCEDURE_NAME_[([*paramètre*] [**,**[*paramètre*]]...)]}</span><span class="sxs-lookup"><span data-stu-id="4aefb-110">{[**?=**]**call**_procedure_name_[([*parameter*][**,**[*parameter*]]...)]}</span></span>  
  
 <span data-ttu-id="4aefb-111">où *PROCEDURE_NAME* spécifie le nom d’une procédure et un *paramètre* spécifie un paramètre de procédure.</span><span class="sxs-lookup"><span data-stu-id="4aefb-111">where *procedure_name* specifies the name of a procedure and *parameter* specifies a procedure parameter.</span></span> <span data-ttu-id="4aefb-112">Les paramètres nommés sont pris en charge uniquement dans les instructions à l'aide de la séquence d'échappement ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="4aefb-112">Named parameters are only supported in statements using the ODBC CALL escape sequence.</span></span>  
  
 <span data-ttu-id="4aefb-113">Une procédure peut avoir zéro, un ou plusieurs paramètres.</span><span class="sxs-lookup"><span data-stu-id="4aefb-113">A procedure can have zero or more parameters.</span></span> <span data-ttu-id="4aefb-114">Elle peut également retourner une valeur (comme l'indique le marqueur de paramètre optionnel ?= au début de la syntaxe).</span><span class="sxs-lookup"><span data-stu-id="4aefb-114">It can also return a value (as indicated by the optional parameter marker ?= at the start of the syntax).</span></span> <span data-ttu-id="4aefb-115">Si un paramètre est un paramètre d'entrée ou d'entrée/sortie, ce peut être un littéral ou un marqueur de paramètre.</span><span class="sxs-lookup"><span data-stu-id="4aefb-115">If a parameter is an input or an input/output parameter, it can be a literal or a parameter marker.</span></span> <span data-ttu-id="4aefb-116">Si le paramètre est un paramètre de sortie, ce doit être un marqueur de paramètre car la sortie est inconnue.</span><span class="sxs-lookup"><span data-stu-id="4aefb-116">If the parameter is an output parameter, it must be a parameter marker because the output is unknown.</span></span> <span data-ttu-id="4aefb-117">Les marqueurs de paramètres doivent être liés à [SQLBindParameter](../../relational-databases/native-client-odbc-api/sqlbindparameter.md) avant l’exécution de l’instruction d’appel de procédure.</span><span class="sxs-lookup"><span data-stu-id="4aefb-117">Parameter markers must be bound with [SQLBindParameter](../../relational-databases/native-client-odbc-api/sqlbindparameter.md) before the procedure call statement is executed.</span></span>  
  
 <span data-ttu-id="4aefb-118">Les paramètres d'entrée et d'entrée/sortie peuvent être omis dans les appels de procédure.</span><span class="sxs-lookup"><span data-stu-id="4aefb-118">Input and input/output parameters can be omitted from procedure calls.</span></span> <span data-ttu-id="4aefb-119">Si une procédure est appelée avec des parenthèses mais sans paramètre, le pilote instruit la source de données d'utiliser la valeur par défaut comme premier paramètre.</span><span class="sxs-lookup"><span data-stu-id="4aefb-119">If a procedure is called with parentheses but without any parameters, the driver instructs the data source to use the default value for the first parameter.</span></span> <span data-ttu-id="4aefb-120">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4aefb-120">For example:</span></span>  
  
 <span data-ttu-id="4aefb-121">{**call** _PROCEDURE_NAME_**()**}</span><span class="sxs-lookup"><span data-stu-id="4aefb-121">{**call** _procedure_name_**( )**}</span></span>  
  
 <span data-ttu-id="4aefb-122">Si la procédure n'a pas de paramètre, elle peut échouer.</span><span class="sxs-lookup"><span data-stu-id="4aefb-122">If the procedure does not have any parameters, the procedure can fail.</span></span> <span data-ttu-id="4aefb-123">Si une procédure est appelée sans parenthèses, le pilote n'envoie aucune valeur de paramètre.</span><span class="sxs-lookup"><span data-stu-id="4aefb-123">If a procedure is called without parentheses, the driver does not send any parameter values.</span></span> <span data-ttu-id="4aefb-124">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4aefb-124">For example:</span></span>  
  
 <span data-ttu-id="4aefb-125">{**call** _PROCEDURE_NAME_}</span><span class="sxs-lookup"><span data-stu-id="4aefb-125">{**call** _procedure_name_}</span></span>  
  
 <span data-ttu-id="4aefb-126">Des littéraux peuvent être spécifiés comme paramètres d'entrée et d'entrée/sortie dans les appels de procédure.</span><span class="sxs-lookup"><span data-stu-id="4aefb-126">Literals can be specified for input and input/output parameters in procedure calls.</span></span> <span data-ttu-id="4aefb-127">Par exemple, la procédure InsertOrder possède cinq paramètres d'entrée.</span><span class="sxs-lookup"><span data-stu-id="4aefb-127">For example, the procedure InsertOrder has five input parameters.</span></span> <span data-ttu-id="4aefb-128">L'appel suivant à InsertOrder omet le premier paramètre, fournit un littéral pour le deuxième paramètre et utilise un marqueur de paramètre pour les troisième, quatrième et cinquième paramètres.</span><span class="sxs-lookup"><span data-stu-id="4aefb-128">The following call to InsertOrder omits the first parameter, provides a literal for the second parameter, and uses a parameter marker for the third, fourth, and fifth parameters.</span></span> <span data-ttu-id="4aefb-129">(Les paramètres sont numérotés de façon séquentielle, en commençant par la valeur 1.)</span><span class="sxs-lookup"><span data-stu-id="4aefb-129">(Parameters are numbered sequentially, beginning with a value of 1.)</span></span>  
  
```  
{call InsertOrder(, 10, ?, ?, ?)}  
```  
  
 <span data-ttu-id="4aefb-130">Notez que si un paramètre est omis, la virgule qui le sépare des autres paramètres doit encore apparaître.</span><span class="sxs-lookup"><span data-stu-id="4aefb-130">Note that if a parameter is omitted, the comma delimiting it from other parameters must still appear.</span></span> <span data-ttu-id="4aefb-131">Si un paramètre d'entrée ou d'entrée/sortie est omis, la procédure utilise la valeur par défaut du paramètre.</span><span class="sxs-lookup"><span data-stu-id="4aefb-131">If an input or input/output parameter is omitted, the procedure uses the default value of the parameter.</span></span> <span data-ttu-id="4aefb-132">D'autres façons de spécifier la valeur par défaut d'un paramètre d'entrée ou d'entrée/sortie consistent à affecter la valeur SQL_DEFAULT_PARAM à la mémoire tampon de l'indicateur/longueur associée au paramètre ou à utiliser le mot clé DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="4aefb-132">Other ways to specify the default value of an input or input/output parameter are to set the value of the length/indicator buffer bound to the parameter to SQL_DEFAULT_PARAM, or to use the DEFAULT keyword.</span></span>  
  
 <span data-ttu-id="4aefb-133">Si un paramètre d'entrée/sortie est omis ou si un littéral est fourni comme paramètre, le pilote ignore la valeur de sortie.</span><span class="sxs-lookup"><span data-stu-id="4aefb-133">If an input/output parameter is omitted, or if a literal is supplied for the parameter, the driver discards the output value.</span></span> <span data-ttu-id="4aefb-134">De la même façon, si le marqueur de paramètre pour la valeur de retour d'une procédure est omis, le pilote ignore la valeur de retour.</span><span class="sxs-lookup"><span data-stu-id="4aefb-134">Similarly, if the parameter marker for the return value of a procedure is omitted, the driver discards the return value.</span></span> <span data-ttu-id="4aefb-135">Enfin, si une application spécifie un paramètre de valeur de retour pour une procédure qui ne renvoie pas de valeur, le pilote affecte la valeur SQL_NULL_DATA à la mémoire tampon de l'indicateur/longueur associée au paramètre.</span><span class="sxs-lookup"><span data-stu-id="4aefb-135">Finally, if an application specifies a return value parameter for a procedure that does not return a value, the driver sets the value of the length/indicator buffer bound to the parameter to SQL_NULL_DATA.</span></span>  
  
## <a name="delimiters-in-call-statements"></a><span data-ttu-id="4aefb-136">Délimiteurs dans les instructions CALL</span><span class="sxs-lookup"><span data-stu-id="4aefb-136">Delimiters in CALL Statements</span></span>  
 <span data-ttu-id="4aefb-137">Le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client prend en charge par défaut également une option de compatibilité spécifique à la séquence d'échappement ODBC { CALL }.</span><span class="sxs-lookup"><span data-stu-id="4aefb-137">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver by default also supports a compatibility option specific to the ODBC { CALL } escape sequence.</span></span> <span data-ttu-id="4aefb-138">Le pilote accepte les instructions CALL avec un jeu unique de guillemets doubles délimitant le nom complet de la procédure stockée :</span><span class="sxs-lookup"><span data-stu-id="4aefb-138">The driver accepts CALL statements with only a single set of double quotation marks delimiting the entire stored procedure name:</span></span>  
  
```  
{ CALL "master.dbo.sp_who" }  
```  
  
 <span data-ttu-id="4aefb-139">Par défaut, le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client accepte également des instructions CALL qui suivent les règles ISO et mettent chaque identificateur entre guillemets doubles :</span><span class="sxs-lookup"><span data-stu-id="4aefb-139">By default the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver also accepts CALL statements that follow the ISO rules and enclose each identifier in double quotation marks:</span></span>  
  
```  
{ CALL "master"."dbo"."sp_who" }  
```  
  
 <span data-ttu-id="4aefb-140">Lors d'une exécution avec les paramètres par défaut, toutefois, le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ne prend pas en charge l'utilisation de l'une ou de l'autre forme d'identificateurs entre guillemets avec des identificateurs qui contiennent des caractères non spécifiés comme légaux dans des identificateurs définis par la norme ISO.</span><span class="sxs-lookup"><span data-stu-id="4aefb-140">When running with the default settings, however, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not support using either form of quoted identifier with identifiers that contain characters not specified as legal in identifiers by the ISO standard.</span></span> <span data-ttu-id="4aefb-141">Par exemple, le pilote ne peut pas accéder à une procédure stockée nommée **« My. proc »** à l’aide d’une instruction call avec des identificateurs entre guillemets :</span><span class="sxs-lookup"><span data-stu-id="4aefb-141">For example, the driver cannot access a stored procedure named **"My.Proc"** using a CALL statement with quoted identifiers:</span></span>  
  
```  
{ CALL "MyDB"."MyOwner"."My.Proc" }  
```  
  
 <span data-ttu-id="4aefb-142">Cette instruction est interprétée par le pilote comme :</span><span class="sxs-lookup"><span data-stu-id="4aefb-142">This statement is interpreted by the driver as:</span></span>  
  
```  
{ CALL MyDB.MyOwner.My.Proc }  
```  
  
 <span data-ttu-id="4aefb-143">Le serveur génère une erreur indiquant qu’un serveur lié nommé **MyDB** n’existe pas.</span><span class="sxs-lookup"><span data-stu-id="4aefb-143">The server raises an error that a linked server named **MyDB** does not exist.</span></span>  
  
 <span data-ttu-id="4aefb-144">Ce problème ne se pose pas lors de l'utilisation d'identificateurs entre parenthèses et l'instruction suivante est interprétée correctement :</span><span class="sxs-lookup"><span data-stu-id="4aefb-144">The issue does not exist when using bracketed identifiers, this statement is interpreted correctly:</span></span>  
  
```  
{ CALL [MyDB].[MyOwner].[My.Table] }  
```  
  
## <a name="see-also"></a><span data-ttu-id="4aefb-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4aefb-145">See Also</span></span>  
 [<span data-ttu-id="4aefb-146">Exécution de procédures stockées</span><span class="sxs-lookup"><span data-stu-id="4aefb-146">Running Stored Procedures</span></span>](../../relational-databases/native-client-odbc-stored-procedures/running-stored-procedures.md)  
  
  
