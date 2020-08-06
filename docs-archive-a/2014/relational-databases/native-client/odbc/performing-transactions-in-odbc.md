---
title: Transactions dans ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, transactions
- transactions [ODBC]
- ODBC, transactions
ms.assetid: c5a87fa5-827a-4e6f-a0d9-924bac881eb0
author: rothja
ms.author: jroth
ms.openlocfilehash: 386b248edfdb6e0ac5eb97b3aeb6c0bbc505a5a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602802"
---
# <a name="transactions-in-odbc"></a><span data-ttu-id="5a269-102">Transactions dans ODBC</span><span class="sxs-lookup"><span data-stu-id="5a269-102">Transactions in ODBC</span></span>
  <span data-ttu-id="5a269-103">Les transactions dans ODBC sont gérées connexion par connexion.</span><span class="sxs-lookup"><span data-stu-id="5a269-103">Transactions in ODBC are managed at the connection level.</span></span> <span data-ttu-id="5a269-104">Lorsqu'une application termine une transaction, elle valide ou restaure tout le travail effectué par le biais de tous les handles d'instruction sur cette connexion.</span><span class="sxs-lookup"><span data-stu-id="5a269-104">When an application completes a transaction, it commits or rolls back all work completed through all statement handles on that connection.</span></span> <span data-ttu-id="5a269-105">Pour valider ou restaurer une transaction, les applications doivent appeler [SQLEndTran](../../native-client-odbc-api/sqlendtran.md) au lieu de soumettre une instruction COMMIT ou ROLLBACK.</span><span class="sxs-lookup"><span data-stu-id="5a269-105">To commit or roll back a transaction, applications should call [SQLEndTran](../../native-client-odbc-api/sqlendtran.md) instead of submitting a COMMIT or ROLLBACK statement.</span></span>  
  
 <span data-ttu-id="5a269-106">Une application appelle [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) pour basculer entre les deux modes ODBC de gestion des transactions :</span><span class="sxs-lookup"><span data-stu-id="5a269-106">An application calls [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) to switch between the two ODBC modes of managing transactions:</span></span>  
  
-   <span data-ttu-id="5a269-107">Mode de validation automatique</span><span class="sxs-lookup"><span data-stu-id="5a269-107">Autocommit mode</span></span>  
  
     <span data-ttu-id="5a269-108">Chaque instruction est validée automatiquement lorsqu'elle est effectuée avec succès.</span><span class="sxs-lookup"><span data-stu-id="5a269-108">Each statement is automatically committed when it is completed successfully.</span></span> <span data-ttu-id="5a269-109">Lorsque vous utilisez le mode de validation automatique, aucune autre fonction de gestion des transactions n'est requise.</span><span class="sxs-lookup"><span data-stu-id="5a269-109">When you run in autocommit mode, no other transaction management functions are required.</span></span>  
  
-   <span data-ttu-id="5a269-110">Mode de validation manuelle</span><span class="sxs-lookup"><span data-stu-id="5a269-110">Manual-commit mode</span></span>  
  
     <span data-ttu-id="5a269-111">Toutes les instructions exécutées sont incluses dans la même transaction jusqu'à ce qu'elle soit arrêtée spécifiquement en appelant **SQLEndTran**.</span><span class="sxs-lookup"><span data-stu-id="5a269-111">All executed statements are included in the same transaction until it is specifically stopped by calling **SQLEndTran**.</span></span>  
  
 <span data-ttu-id="5a269-112">Le mode de validation automatique est le mode de gestion par défaut des transactions pour ODBC.</span><span class="sxs-lookup"><span data-stu-id="5a269-112">Autocommit mode is the default transaction mode for ODBC.</span></span> <span data-ttu-id="5a269-113">Lorsqu'une connexion est établie, elle est en mode de validation automatique jusqu'à ce que **SQLSetConnectAttr** soit appelé pour basculer en mode de validation manuelle en désactivant le mode de validation automatique.</span><span class="sxs-lookup"><span data-stu-id="5a269-113">When a connection is made, it is in autocommit mode until **SQLSetConnectAttr** is called to switch to manual-commit mode by setting autocommit mode off.</span></span> <span data-ttu-id="5a269-114">Lorsqu'une application désactive la validation automatique, l'instruction suivante envoyée à la base de données démarre une transaction.</span><span class="sxs-lookup"><span data-stu-id="5a269-114">When an application turns autocommit off, the next statement sent to the database starts a transaction.</span></span> <span data-ttu-id="5a269-115">La transaction reste ensuite active jusqu'à ce que l'application appelle **SQLEndTran** avec les options SQL_COMMIT ou SQL_ROLLBACK.</span><span class="sxs-lookup"><span data-stu-id="5a269-115">The transaction then remains in effect until the application calls **SQLEndTran** with either the SQL_COMMIT or SQL_ROLLBACK options.</span></span> <span data-ttu-id="5a269-116">La commande envoyée à la base de données après **SQLEndTran** démarre la transaction suivante.</span><span class="sxs-lookup"><span data-stu-id="5a269-116">The command sent to the database after **SQLEndTran** starts the next transaction.</span></span>  
  
 <span data-ttu-id="5a269-117">Si une application bascule du mode de validation manuelle au mode de validation automatique, le pilote valide toutes les transactions actuellement ouvertes sur la connexion.</span><span class="sxs-lookup"><span data-stu-id="5a269-117">If an application switches from manual-commit to autocommit mode, the driver commits any transactions currently open on the connection.</span></span>  
  
 <span data-ttu-id="5a269-118">Les applications ODBC ne doivent pas utiliser d'instructions de transaction Transact-SQL telles que BEGIN TRANSACTION, COMMIT TRANSACTION ou ROLLBACK TRANSACTION, car cela peut provoquer un comportement indéterminé dans le pilote.</span><span class="sxs-lookup"><span data-stu-id="5a269-118">ODBC applications should not use Transact-SQL transaction statements such as BEGIN TRANSACTION, COMMIT TRANSACTION, or ROLLBACK TRANSACTION because this can cause indeterminate behavior in the driver.</span></span> <span data-ttu-id="5a269-119">Une application ODBC doit s'exécuter en mode de validation automatique et ne doit pas utiliser les instructions ni les fonctions de gestion des transactions, ou elle doit s'exécuter en mode de validation manuelle et utiliser la fonction ODBC **SQLEndTran** pour valider ou restaurer des transactions.</span><span class="sxs-lookup"><span data-stu-id="5a269-119">An ODBC application should run in autocommit mode and not use any transaction management functions or statements, or run in manual-commit mode and use the ODBC **SQLEndTran** function to either commit or roll back transactions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a269-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5a269-120">See Also</span></span>  
 [<span data-ttu-id="5a269-121">Exécution de transactions &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="5a269-121">Performing Transactions &#40;ODBC&#41;</span></span>](../../../database-engine/dev-guide/performing-transactions-odbc.md)  
  
  
