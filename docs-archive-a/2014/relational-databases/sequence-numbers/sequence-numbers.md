---
title: Numéros séquentiels | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- sequence number object, overview
- sequence [Database Engine]
- autonumbers, sequences
- sequence numbers [SQL Server]
- sequence number object
ms.assetid: c900e30d-2fd3-4d5f-98ee-7832f37e79d1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6c65b4df915a85cf0ec7c7c0c8c0ff9f6607ad96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709047"
---
# <a name="sequence-numbers"></a><span data-ttu-id="8579b-102">Numéros séquentiels</span><span class="sxs-lookup"><span data-stu-id="8579b-102">Sequence Numbers</span></span>
  <span data-ttu-id="8579b-103">Une séquence est un objet lié par schéma défini par l'utilisateur qui génère une séquence de valeurs numériques d'après la spécification avec laquelle la séquence a été créée.</span><span class="sxs-lookup"><span data-stu-id="8579b-103">A sequence is a user-defined schema-bound object that generates a sequence of numeric values according to the specification with which the sequence was created.</span></span> <span data-ttu-id="8579b-104">La séquence de valeurs numériques est générée dans un ordre croissant ou décroissant à un intervalle défini et peut effectuer un cycle (répétition) selon la demande.</span><span class="sxs-lookup"><span data-stu-id="8579b-104">The sequence of numeric values is generated in an ascending or descending order at a defined interval and may cycle (repeat) as requested.</span></span> <span data-ttu-id="8579b-105">Les séquences, contrairement aux colonnes d'identité, ne sont pas associées à des tables.</span><span class="sxs-lookup"><span data-stu-id="8579b-105">Sequences, unlike identity columns, are not associated with tables.</span></span> <span data-ttu-id="8579b-106">Une application fait référence à un objet séquence pour recevoir sa valeur suivante.</span><span class="sxs-lookup"><span data-stu-id="8579b-106">An application refers to a sequence object to receive its next value.</span></span> <span data-ttu-id="8579b-107">La relation entre les séquences et les tables est contrôlée par l'application.</span><span class="sxs-lookup"><span data-stu-id="8579b-107">The relationship between sequences and tables is controlled by the application.</span></span> <span data-ttu-id="8579b-108">Les applications utilisateur peuvent référencer un objet séquence et coordonner les clés des valeurs entre plusieurs lignes et tables.</span><span class="sxs-lookup"><span data-stu-id="8579b-108">User applications can reference a sequence object and coordinate the values keys across multiple rows and tables.</span></span>  
  
 <span data-ttu-id="8579b-109">Une séquence est créée indépendamment des tables à l’aide de l’instruction **CREATE SEQUENCE** .</span><span class="sxs-lookup"><span data-stu-id="8579b-109">A sequence is created independently of the tables by using the **CREATE SEQUENCE** statement.</span></span> <span data-ttu-id="8579b-110">Des options vous permettent de contrôler l'incrémentation, les valeurs maximales et minimales, le point de départ, la fonction de redémarrage automatique et la mise en cache afin d'améliorer les performances.</span><span class="sxs-lookup"><span data-stu-id="8579b-110">Options enable you to control the increment, maximum and minimum values, starting point, automatic restarting capability, and caching to improve performance.</span></span> <span data-ttu-id="8579b-111">Pour plus d’informations sur ces options, consultez [CREATE SEQUENCE](/sql/t-sql/statements/create-sequence-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8579b-111">For information about the options, see [CREATE SEQUENCE](/sql/t-sql/statements/create-sequence-transact-sql).</span></span>  
  
 <span data-ttu-id="8579b-112">Au lieu d’utiliser des valeurs de colonne d'identité, qui sont générées lors de l’insertion de lignes, une application peut obtenir le numéro séquentiel suivant avant d’insérer une ligne en appelant la fonction [NEXT VALUE FOR](/sql/t-sql/functions/next-value-for-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="8579b-112">Unlike identity column values, which are generated when rows are inserted, an application can obtain the next sequence number before inserting the row by calling the [NEXT VALUE FOR](/sql/t-sql/functions/next-value-for-transact-sql) function.</span></span> <span data-ttu-id="8579b-113">Le numéro séquentiel est alloué lors de l'appel de NEXT VALUE FOR, même si ce nombre n'est jamais inséré dans une table.</span><span class="sxs-lookup"><span data-stu-id="8579b-113">The sequence number is allocated when NEXT VALUE FOR is called even if the number is never inserted into a table.</span></span> <span data-ttu-id="8579b-114">La fonction NEXT VALUE FOR peut être utilisée comme valeur par défaut pour une colonne dans une définition de table.</span><span class="sxs-lookup"><span data-stu-id="8579b-114">The NEXT VALUE FOR function can be used as the default value for a column in a table definition.</span></span> <span data-ttu-id="8579b-115">Utilisez [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql) pour obtenir une plage de plusieurs numéros séquentiels à la fois.</span><span class="sxs-lookup"><span data-stu-id="8579b-115">Use [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql) to get a range of multiple sequence numbers at once.</span></span>  
  
 <span data-ttu-id="8579b-116">Une séquence peut être définie comme n'importe quel type de données integer.</span><span class="sxs-lookup"><span data-stu-id="8579b-116">A sequence can be defined as any integer data type.</span></span> <span data-ttu-id="8579b-117">Si le type de données n'est pas spécifié, une séquence prend pour valeur par défaut `bigint`.</span><span class="sxs-lookup"><span data-stu-id="8579b-117">If the data type is not specified, a sequence defaults to `bigint`.</span></span>  
  
## <a name="using-sequences"></a><span data-ttu-id="8579b-118">Utilisation de séquences</span><span class="sxs-lookup"><span data-stu-id="8579b-118">Using Sequences</span></span>  
 <span data-ttu-id="8579b-119">Utilisez les séquences à la place des colonnes d'identité dans les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="8579b-119">Use sequences instead of identity columns in the following scenarios:</span></span>  
  
-   <span data-ttu-id="8579b-120">L'application a besoin d'un nombre avant d'effectuer l'insertion dans la table.</span><span class="sxs-lookup"><span data-stu-id="8579b-120">The application requires a number before the insert into the table is made.</span></span>  
  
-   <span data-ttu-id="8579b-121">L'application requiert le partage d'une série de nombres unique entre plusieurs tables ou plusieurs colonnes dans une table.</span><span class="sxs-lookup"><span data-stu-id="8579b-121">The application requires sharing a single series of numbers between multiple tables or multiple columns within a table.</span></span>  
  
-   <span data-ttu-id="8579b-122">L'application doit redémarrer la série de nombres lorsqu'un nombre spécifié est atteint.</span><span class="sxs-lookup"><span data-stu-id="8579b-122">The application must restart the number series when a specified number is reached.</span></span> <span data-ttu-id="8579b-123">Par exemple, après avoir affecté les valeurs 1 à 10, l'application recommence à affecter les valeurs 1 à 10.</span><span class="sxs-lookup"><span data-stu-id="8579b-123">For example, after assigning values 1 through 10, the application starts assigning values 1 through 10 again.</span></span>  
  
-   <span data-ttu-id="8579b-124">L'application requiert le tri des valeurs de séquence par un autre champ.</span><span class="sxs-lookup"><span data-stu-id="8579b-124">The application requires sequence values to be sorted by another field.</span></span> <span data-ttu-id="8579b-125">La fonction NEXT VALUE FOR peut appliquer la clause OVER à l'appel de fonction.</span><span class="sxs-lookup"><span data-stu-id="8579b-125">The NEXT VALUE FOR function can apply the OVER clause to the function call.</span></span> <span data-ttu-id="8579b-126">La clause OVER garantit que les valeurs retournées sont générées dans l'ordre de la clause ORDER BY de la clause OVER.</span><span class="sxs-lookup"><span data-stu-id="8579b-126">The OVER clause guarantees that the values returned are generated in the order of the OVER clause's ORDER BY clause.</span></span>  
  
-   <span data-ttu-id="8579b-127">Une application requiert que plusieurs nombres soient affectés en même temps.</span><span class="sxs-lookup"><span data-stu-id="8579b-127">An application requires multiple numbers to be assigned at the same time.</span></span> <span data-ttu-id="8579b-128">Par exemple, une application doit réserver cinq numéros séquentiels.</span><span class="sxs-lookup"><span data-stu-id="8579b-128">For example, an application needs to reserve five sequential numbers.</span></span> <span data-ttu-id="8579b-129">La demande de valeurs d'identité peut provoquer des intervalles dans la série si des nombres ont été émis pour d'autres processus simultanément.</span><span class="sxs-lookup"><span data-stu-id="8579b-129">Requesting identity values could result in gaps in the series if other processes were simultaneously issued numbers.</span></span> <span data-ttu-id="8579b-130">L’appel de sp_sequence_get_range permet d’extraire plusieurs nombres à la fois dans la séquence.</span><span class="sxs-lookup"><span data-stu-id="8579b-130">Calling sp_sequence_get_range can retrieve several numbers in the sequence at once.</span></span>  
  
-   <span data-ttu-id="8579b-131">Vous devez modifier la spécification de la séquence, telle que la valeur de l'incrément.</span><span class="sxs-lookup"><span data-stu-id="8579b-131">You need to change the specification of the sequence, such as the increment value.</span></span>  
  
## <a name="limitations"></a><span data-ttu-id="8579b-132">Limites</span><span class="sxs-lookup"><span data-stu-id="8579b-132">Limitations</span></span>  
 <span data-ttu-id="8579b-133">Contrairement aux colonnes d'identité, dont les valeurs ne peuvent pas être modifiées, les valeurs de séquence ne sont pas protégées automatiquement après leur insertion dans la table.</span><span class="sxs-lookup"><span data-stu-id="8579b-133">Unlike identity columns, whose values cannot be changed, sequence values are not automatically protected after insertion into the table.</span></span> <span data-ttu-id="8579b-134">Pour empêcher toute modification des valeurs de séquence, utilisez un déclencheur de mise à jour sur la table pour annuler les modifications.</span><span class="sxs-lookup"><span data-stu-id="8579b-134">To prevent sequence values from being changed, use an update trigger on the table to roll back changes.</span></span>  
  
 <span data-ttu-id="8579b-135">L'unicité ne s'applique pas automatiquement aux valeurs de séquence.</span><span class="sxs-lookup"><span data-stu-id="8579b-135">Uniqueness is not automatically enforced for sequence values.</span></span> <span data-ttu-id="8579b-136">La possibilité de réutiliser des valeurs de séquence est un processus normal.</span><span class="sxs-lookup"><span data-stu-id="8579b-136">The ability to reuse sequence values is by design.</span></span> <span data-ttu-id="8579b-137">Si les valeurs de séquence dans une table doivent obligatoirement être uniques, créez un index unique sur la colonne.</span><span class="sxs-lookup"><span data-stu-id="8579b-137">If sequence values in a table are required to be unique, create a unique index on the column.</span></span> <span data-ttu-id="8579b-138">Si les valeurs de séquence d'une table doivent obligatoirement être uniques dans l'ensemble d'un groupe de tables, créez des déclencheurs pour empêcher les doublons provoqués par les instructions UPDATE ou les cycles de numéros séquentiels.</span><span class="sxs-lookup"><span data-stu-id="8579b-138">If sequence values in a table are required to be unique throughout a group of tables, create triggers to prevent duplicates caused by update statements or sequence number cycling.</span></span>  
  
 <span data-ttu-id="8579b-139">L'objet séquence génère des nombres en fonction de sa définition, mais l'objet séquence ne contrôle pas la façon dont les nombres sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="8579b-139">The sequence object generates numbers according to its definition, but the sequence object does not control how the numbers are used.</span></span> <span data-ttu-id="8579b-140">Les numéros séquentiels insérés dans une table peuvent présenter des intervalles en cas d'annulation d'une transaction, de partage d'un objet séquence par plusieurs tables ou lorsque des numéros séquentiels sont alloués sans les utiliser dans les tables.</span><span class="sxs-lookup"><span data-stu-id="8579b-140">Sequence numbers inserted into a table can have gaps when a transaction is rolled back, when a sequence object is shared by multiple tables, or when sequence numbers are allocated without using them in tables.</span></span> <span data-ttu-id="8579b-141">En cas de création avec l'option CACHE, un arrêt inattendu, tel qu'une panne de courant, peut conduire à la perte des numéros séquentiels dans le cache.</span><span class="sxs-lookup"><span data-stu-id="8579b-141">When created with the CACHE option, an unexpected shutdown, such as a power failure, can lose the sequence numbers in the cache.</span></span>  
  
 <span data-ttu-id="8579b-142">Si plusieurs instances de la fonction `NEXT VALUE FOR` spécifient le même générateur de séquence dans une instruction [!INCLUDE[tsql](../../../includes/tsql-md.md)] unique, toutes ces instances retournent la même valeur pour une ligne donnée traitée par cette instruction [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8579b-142">If there are multiple instances of the `NEXT VALUE FOR` function specifying the same sequence generator within a single [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement, all those instances return the same value for a given row processed by that [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="8579b-143">Ce comportement est cohérent avec la norme ANSI.</span><span class="sxs-lookup"><span data-stu-id="8579b-143">This behavior is consistent with the ANSI standard.</span></span>  
  
## <a name="typical-use"></a><span data-ttu-id="8579b-144">Utilisation courante</span><span class="sxs-lookup"><span data-stu-id="8579b-144">Typical Use</span></span>  
 <span data-ttu-id="8579b-145">Pour créer un numéro séquentiel entier qui incrémente par 1 de -2 147 483 648 à 2 147 483 647, utilisez l'instruction suivante.</span><span class="sxs-lookup"><span data-stu-id="8579b-145">To create an integer sequence number that increments by 1 from -2,147,483,648 to 2,147,483,647, use the following statement.</span></span>  
  
```  
CREATE SEQUENCE Schema.SequenceName  
    AS int  
    INCREMENT BY 1 ;  
```  
  
 <span data-ttu-id="8579b-146">Pour créer un numéro séquentiel entier similaire à une colonne d'identité qui incrémente par 1 de 1 à -2 147 483 648 à 2 147 483 647, utilisez l'instruction suivante.</span><span class="sxs-lookup"><span data-stu-id="8579b-146">To create an integer sequence number similar to an identity column that increments by 1 from 1 to 2,147,483,647, use the following statement.</span></span>  
  
```  
CREATE SEQUENCE Schema.SequenceName  
    AS int  
    START WITH 1  
    INCREMENT BY 1 ;  
  
```  
  
## <a name="managing-sequences"></a><span data-ttu-id="8579b-147">Gestion de séquences</span><span class="sxs-lookup"><span data-stu-id="8579b-147">Managing Sequences</span></span>  
 <span data-ttu-id="8579b-148">Pour plus d’informations sur les séquences, interrogez [sys.sequences](/sql/relational-databases/system-catalog-views/sys-sequences-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8579b-148">For information about sequences, query [sys.sequences](/sql/relational-databases/system-catalog-views/sys-sequences-transact-sql).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="8579b-149">Exemples</span><span class="sxs-lookup"><span data-stu-id="8579b-149">Examples</span></span>  
 <span data-ttu-id="8579b-150">D’autres exemples sont fournis dans les rubriques [CREATE SEQUENCE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-sequence-transact-sql), [NEXT VALUE FOR &#40;Transact-SQL&#41;](/sql/t-sql/functions/next-value-for-transact-sql) et [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8579b-150">There are additional examples in the topics [CREATE SEQUENCE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-sequence-transact-sql), [NEXT VALUE FOR &#40;Transact-SQL&#41;](/sql/t-sql/functions/next-value-for-transact-sql), and [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql).</span></span>  
  
### <a name="a-using-a-sequence-number-in-a-single-table"></a><span data-ttu-id="8579b-151">R.</span><span class="sxs-lookup"><span data-stu-id="8579b-151">A.</span></span> <span data-ttu-id="8579b-152">Utilisation d'un numéro séquentiel dans une table individuelle</span><span class="sxs-lookup"><span data-stu-id="8579b-152">Using a sequence number in a single table</span></span>  
 <span data-ttu-id="8579b-153">L’exemple suivant crée un schéma nommé Test, une table nommée Orders et une séquence nommée CountBy1, puis insère des lignes dans la table à l’aide de la fonction NEXT VALUE FOR.</span><span class="sxs-lookup"><span data-stu-id="8579b-153">The following example creates a schema named Test, a table named Orders, and a sequence named CountBy1, and then inserts rows into the table using the NEXT VALUE FOR function.</span></span>  
  
```  
--Create the Test schema  
CREATE SCHEMA Test ;  
GO  
  
-- Create a table  
CREATE TABLE Test.Orders  
    (OrderID int PRIMARY KEY,  
    Name varchar(20) NOT NULL,  
    Qty int NOT NULL);  
GO  
  
-- Create a sequence  
CREATE SEQUENCE Test.CountBy1  
    START WITH 1  
    INCREMENT BY 1 ;  
GO  
  
-- Insert three records  
INSERT Test.Orders (OrderID, Name, Qty)  
    VALUES (NEXT VALUE FOR Test.CountBy1, 'Tire', 2) ;  
INSERT test.Orders (OrderID, Name, Qty)  
    VALUES (NEXT VALUE FOR Test.CountBy1, 'Seat', 1) ;  
INSERT test.Orders (OrderID, Name, Qty)  
    VALUES (NEXT VALUE FOR Test.CountBy1, 'Brake', 1) ;  
GO  
  
-- View the table  
SELECT * FROM Test.Orders ;  
GO  
```  
  
 [!INCLUDE[ssResult](../../../includes/ssresult-md.md)]  
  
 `OrderID  Name    Qty`  
  
 `1        Tire    2`  
  
 `2        Seat    1`  
  
 `3        Brake   1`  
  
### <a name="b-calling-next-value-for-before-inserting-a-row"></a><span data-ttu-id="8579b-154">B.</span><span class="sxs-lookup"><span data-stu-id="8579b-154">B.</span></span> <span data-ttu-id="8579b-155">Appel de la fonction NEXT VALUE FOR avant d'insérer une ligne</span><span class="sxs-lookup"><span data-stu-id="8579b-155">Calling NEXT VALUE FOR before inserting a row</span></span>  
 <span data-ttu-id="8579b-156">À l'aide de la table `Orders` créée dans l'exemple A, l'exemple suivant déclare une variable nommée `@nextID`, puis utilise la fonction NEXT VALUE FOR pour affecter à la variable le numéro séquentiel disponible suivant.</span><span class="sxs-lookup"><span data-stu-id="8579b-156">Using the `Orders` table created in example A, the following example declares a variable named `@nextID`, and then uses the NEXT VALUE FOR function to set the variable to the next available sequence number.</span></span> <span data-ttu-id="8579b-157">L'application est censée effectuer un traitement de la commande, tel que fournir au client un numéro `OrderID` de commande potentielle, puis valider la commande.</span><span class="sxs-lookup"><span data-stu-id="8579b-157">The application is presumed to do some processing of the order, such as providing the customer with the `OrderID` number of their potential order, and then validates the order.</span></span> <span data-ttu-id="8579b-158">Quelle que soit la durée du traitement ou quel que soit le nombre de commandes supplémentaires ajoutées au cours du processus, le numéro d'origine est conservé pour être utilisé par cette connexion.</span><span class="sxs-lookup"><span data-stu-id="8579b-158">No matter how long this processing might take, or how many other orders are added during the process, the original number is preserved for use by this connection.</span></span> <span data-ttu-id="8579b-159">Enfin, l'instruction `INSERT` ajoute la commande à la table `Orders` .</span><span class="sxs-lookup"><span data-stu-id="8579b-159">Finally, the `INSERT` statement adds the order to the `Orders` table.</span></span>  
  
```  
DECLARE @NextID int ;  
SET @NextID = NEXT VALUE FOR Test.CountBy1;  
-- Some work happens  
INSERT Test.Orders (OrderID, Name, Qty)  
    VALUES (@NextID, 'Rim', 2) ;  
GO  
  
```  
  
### <a name="c-using-a-sequence-number-in-multiple-tables"></a><span data-ttu-id="8579b-160">C.</span><span class="sxs-lookup"><span data-stu-id="8579b-160">C.</span></span> <span data-ttu-id="8579b-161">Utilisation d'un numéro séquentiel dans plusieurs tables</span><span class="sxs-lookup"><span data-stu-id="8579b-161">Using a sequence number in multiple tables</span></span>  
 <span data-ttu-id="8579b-162">Cet exemple suppose qu'un processus d'analyse de chaîne de fabrication reçoit une notification des événements qui se produisent dans tout l'atelier.</span><span class="sxs-lookup"><span data-stu-id="8579b-162">This example assumes that a production-line monitoring process receives notification of events that occur throughout the workshop.</span></span> <span data-ttu-id="8579b-163">Chaque événement reçoit un numéro unique `EventID` , à croissance monolithique.</span><span class="sxs-lookup"><span data-stu-id="8579b-163">Each event receives a unique and monotonically increasing `EventID` number.</span></span> <span data-ttu-id="8579b-164">Tous les événements utilisent le même numéro séquentiel `EventID` afin que les rapports qui combinent tous les événements puissent identifier chaque événement de façon unique.</span><span class="sxs-lookup"><span data-stu-id="8579b-164">All events use the same `EventID` sequence number so that reports that combine all events can uniquely identify each event.</span></span> <span data-ttu-id="8579b-165">Cependant les données d'événement sont stockées dans trois tables différentes, selon le type d'événement.</span><span class="sxs-lookup"><span data-stu-id="8579b-165">However the event data is stored in three different tables, depending on the type of event.</span></span> <span data-ttu-id="8579b-166">L’exemple de code crée un schéma nommé `Audit`, une séquence nommée `EventCounter`et trois tables qui utilisent chacune la séquence `EventCounter` comme valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="8579b-166">The code example creates a schema named `Audit`, a sequence named `EventCounter`, and three tables which each use the `EventCounter` sequence as a default value.</span></span> <span data-ttu-id="8579b-167">Puis l'exemple ajoute des lignes aux trois tables et interroge les résultats.</span><span class="sxs-lookup"><span data-stu-id="8579b-167">Then the example adds rows to the three tables and queries the results.</span></span>  
  
```  
CREATE SCHEMA Audit ;  
GO  
CREATE SEQUENCE Audit.EventCounter  
    AS int  
    START WITH 1  
    INCREMENT BY 1 ;  
GO  
  
CREATE TABLE Audit.ProcessEvents  
(  
    EventID int PRIMARY KEY CLUSTERED   
        DEFAULT (NEXT VALUE FOR Audit.EventCounter),  
    EventTime datetime NOT NULL DEFAULT (getdate()),  
    EventCode nvarchar(5) NOT NULL,  
    Description nvarchar(300) NULL  
) ;  
GO  
  
CREATE TABLE Audit.ErrorEvents  
(  
    EventID int PRIMARY KEY CLUSTERED  
        DEFAULT (NEXT VALUE FOR Audit.EventCounter),  
    EventTime datetime NOT NULL DEFAULT (getdate()),  
    EquipmentID int NULL,  
    ErrorNumber int NOT NULL,  
    EventDesc nvarchar(256) NULL  
) ;  
GO  
  
CREATE TABLE Audit.StartStopEvents  
(  
    EventID int PRIMARY KEY CLUSTERED  
        DEFAULT (NEXT VALUE FOR Audit.EventCounter),  
    EventTime datetime NOT NULL DEFAULT (getdate()),  
    EquipmentID int NOT NULL,  
    StartOrStop bit NOT NULL  
) ;  
GO  
  
INSERT Audit.StartStopEvents (EquipmentID, StartOrStop)   
    VALUES (248, 0) ;  
INSERT Audit.StartStopEvents (EquipmentID, StartOrStop)   
    VALUES (72, 0) ;  
INSERT Audit.ProcessEvents (EventCode, Description)   
    VALUES (2735,   
    'Clean room temperature 18 degrees C.') ;  
INSERT Audit.ProcessEvents (EventCode, Description)   
    VALUES (18, 'Spin rate threashold exceeded.') ;  
INSERT Audit.ErrorEvents (EquipmentID, ErrorNumber, EventDesc)   
    VALUES (248, 82, 'Feeder jam') ;  
INSERT Audit.StartStopEvents (EquipmentID, StartOrStop)   
    VALUES (248, 1) ;  
INSERT Audit.ProcessEvents (EventCode, Description)   
    VALUES (1841, 'Central feed in bypass mode.') ;  
-- The following statement combines all events, though not all fields.  
SELECT EventID, EventTime, Description FROM Audit.ProcessEvents   
UNION SELECT EventID, EventTime, EventDesc FROM Audit.ErrorEvents   
UNION SELECT EventID, EventTime,   
CASE StartOrStop   
    WHEN 0 THEN 'Start'   
    ELSE 'Stop'  
END   
FROM Audit.StartStopEvents  
ORDER BY EventID ;  
GO  
  
```  
  
 [!INCLUDE[ssResult](../../../includes/ssresult-md.md)]  
  
 `EventID  EventTime                Description`  
  
 `1        2009-11-02 15:00:51.157  Start`  
  
 `2        2009-11-02 15:00:51.160  Start`  
  
 `3        2009-11-02 15:00:51.167  Clean room temperature 18 degrees C.`  
  
 `4        2009-11-02 15:00:51.167  Spin rate threshold exceeded.`  
  
 `5        2009-11-02 15:00:51.173  Feeder jam`  
  
 `6        2009-11-02 15:00:51.177  Stop`  
  
 `7        2009-11-02 15:00:51.180  Central feed in bypass mode.`  
  
### <a name="d-generating-repeating-sequence-numbers-in-a-result-set"></a><span data-ttu-id="8579b-168">D.</span><span class="sxs-lookup"><span data-stu-id="8579b-168">D.</span></span> <span data-ttu-id="8579b-169">Génération de numéros séquentiels à répétition dans un jeu de résultats</span><span class="sxs-lookup"><span data-stu-id="8579b-169">Generating repeating sequence numbers in a result set</span></span>  
 <span data-ttu-id="8579b-170">L'exemple suivant montre deux fonctionnalités des numéros séquentiels : les cycles et l'utilisation de la fonction `NEXT VALUE FOR` dans une instruction select.</span><span class="sxs-lookup"><span data-stu-id="8579b-170">The following example demonstrates two features of sequence numbers: cycling, and using `NEXT VALUE FOR` in a select statement.</span></span>  
  
```  
CREATE SEQUENCE CountBy5  
   AS tinyint  
    START WITH 1  
    INCREMENT BY 1  
    MINVALUE 1  
    MAXVALUE 5  
    CYCLE ;  
GO  
  
SELECT NEXT VALUE FOR CountBy5 AS SurveyGroup, Name FROM sys.objects ;  
GO  
```  
  
### <a name="e-generating-sequence-numbers-for-a-result-set-by-using-the-over-clause"></a><span data-ttu-id="8579b-171">E.</span><span class="sxs-lookup"><span data-stu-id="8579b-171">E.</span></span> <span data-ttu-id="8579b-172">Génération de numéros séquentiels pour un jeu de résultats à l'aide de la clause OVER</span><span class="sxs-lookup"><span data-stu-id="8579b-172">Generating sequence numbers for a result set by using the OVER clause</span></span>  
 <span data-ttu-id="8579b-173">L'exemple suivant utilise la clause `OVER` pour trier le jeu de résultats par `Name` avant que la colonne de numéros séquentiels soit ajoutée.</span><span class="sxs-lookup"><span data-stu-id="8579b-173">The following example uses the `OVER` clause to sort the result set by `Name` before it adds the sequence number column.</span></span>  
  
```  
USE AdventureWorks2012 ;  
GO  
  
CREATE SCHEMA Samples ;  
GO  
  
CREATE SEQUENCE Samples.IDLabel  
    AS tinyint  
    START WITH 1  
    INCREMENT BY 1 ;  
GO  
  
SELECT NEXT VALUE FOR Samples.IDLabel OVER (ORDER BY Name) AS NutID, ProductID, Name, ProductNumber FROM Production.Product  
WHERE Name LIKE '%nut%' ;  
```  
  
### <a name="f-resetting-the-sequence-number"></a><span data-ttu-id="8579b-174">F.</span><span class="sxs-lookup"><span data-stu-id="8579b-174">F.</span></span> <span data-ttu-id="8579b-175">Réinitialisation de numéros séquentiels</span><span class="sxs-lookup"><span data-stu-id="8579b-175">Resetting the sequence number</span></span>  
 <span data-ttu-id="8579b-176">L'exemple E a utilisé les 79 premiers numéros séquentiels `Samples.IDLabel`</span><span class="sxs-lookup"><span data-stu-id="8579b-176">Example E consumed the first 79 of the `Samples.IDLabel` sequence numbers.</span></span> <span data-ttu-id="8579b-177">(votre version d' `AdventureWorks2012` peut retourner un nombre différent de résultats). Exécutez le code suivant pour utiliser les 79 numéros séquentiels suivants (de 80 à 158).</span><span class="sxs-lookup"><span data-stu-id="8579b-177">(Your version of `AdventureWorks2012` may return a different number of results.) Execute the following to consume the next 79 sequence numbers (80 though 158).</span></span>  
  
```  
SELECT NEXT VALUE FOR Samples.IDLabel OVER (ORDER BY Name) AS NutID, ProductID, Name, ProductNumber FROM Production.Product  
WHERE Name LIKE '%nut%' ;  
```  
  
 <span data-ttu-id="8579b-178">Exécutez l’instruction suivante pour redémarrer la séquence `Samples.IDLabel`.</span><span class="sxs-lookup"><span data-stu-id="8579b-178">Execute the following statement to restart the `Samples.IDLabel` sequence.</span></span>  
  
```  
ALTER SEQUENCE Samples.IDLabel  
RESTART WITH 1 ;  
```  
  
 <span data-ttu-id="8579b-179">Réexécutez l’instruction select pour vérifier que la séquence `Samples.IDLabel` a redémarré à partir du nombre 1.</span><span class="sxs-lookup"><span data-stu-id="8579b-179">Execute the select statement again to verify that the `Samples.IDLabel` sequence restarted with number 1.</span></span>  
  
```  
SELECT NEXT VALUE FOR Samples.IDLabel OVER (ORDER BY Name) AS NutID, ProductID, Name, ProductNumber FROM Production.Product  
WHERE Name LIKE '%nut%' ;  
```  
  
### <a name="g-changing-a-table-from-identity-to-sequence"></a><span data-ttu-id="8579b-180">G.</span><span class="sxs-lookup"><span data-stu-id="8579b-180">G.</span></span> <span data-ttu-id="8579b-181">Modification d'une table d'identité en séquence</span><span class="sxs-lookup"><span data-stu-id="8579b-181">Changing a table from identity to sequence</span></span>  
 <span data-ttu-id="8579b-182">L'exemple suivant crée un schéma et une table contenant trois lignes.</span><span class="sxs-lookup"><span data-stu-id="8579b-182">The following example creates a schema and table containing three rows for the example.</span></span> <span data-ttu-id="8579b-183">L'exemple ajoute ensuite une nouvelle colonne et supprime l'ancienne.</span><span class="sxs-lookup"><span data-stu-id="8579b-183">Then the example adds a new column and drops the old column.</span></span>  
  
```  
-- Create a schema  
CREATE SCHEMA Test ;  
GO  
  
-- Create a table  
CREATE TABLE Test.Department  
    (  
        DepartmentID smallint IDENTITY(1,1) NOT NULL,  
        Name nvarchar(100) NOT NULL,  
        GroupName nvarchar(100) NOT NULL  
    CONSTRAINT PK_Department_DepartmentID PRIMARY KEY CLUSTERED   
         (DepartmentID ASC)   
    ) ;  
GO  
  
-- Insert three rows into the table  
INSERT Test.Department(Name, GroupName)  
    VALUES ('Engineering', 'Research and Development');  
GO  
  
INSERT Test.Department(Name, GroupName)  
    VALUES ('Tool Design', 'Research and Development');  
GO  
  
INSERT Test.Department(Name, GroupName)  
    VALUES ('Sales', 'Sales and Marketing');  
GO  
  
-- View the table that will be changed  
SELECT * FROM Test.Department ;  
GO  
  
-- End of portion creating a sample table  
--------------------------------------------------------  
-- Add the new column that does not have the IDENTITY property  
ALTER TABLE Test.Department   
    ADD DepartmentIDNew smallint NULL  
GO  
  
-- Copy values from the old column to the new column  
UPDATE Test.Department  
    SET DepartmentIDNew = DepartmentID ;  
GO  
  
-- Drop the primary key constraint on the old column  
ALTER TABLE Test.Department  
    DROP CONSTRAINT [PK_Department_DepartmentID];  
-- Drop the old column  
ALTER TABLE Test.Department  
    DROP COLUMN DepartmentID ;  
GO  
  
-- Rename the new column to the old columns name  
EXEC sp_rename 'Test.Department.DepartmentIDNew',   
    'DepartmentID', 'COLUMN';  
GO  
  
-- Change the new column to NOT NULL  
ALTER TABLE Test.Department  
    ALTER COLUMN DepartmentID smallint NOT NULL ;  
-- Add the unique primary key constraint  
ALTER TABLE Test.Department  
    ADD CONSTRAINT PK_Department_DepartmentID PRIMARY KEY CLUSTERED   
         (DepartmentID ASC) ;  
-- Get the highest current value from the DepartmentID column   
-- and create a sequence to use with the column. (Returns 3.)  
SELECT MAX(DepartmentID) FROM Test.Department ;  
-- Use the next desired value (4) as the START WITH VALUE;  
CREATE SEQUENCE Test.DeptSeq  
    AS smallint  
    START WITH 4  
    INCREMENT BY 1 ;  
GO  
  
-- Add a default value for the DepartmentID column  
ALTER TABLE Test.Department  
    ADD CONSTRAINT DefSequence DEFAULT (NEXT VALUE FOR Test.DeptSeq)   
        FOR DepartmentID;  
GO  
  
-- View the result  
SELECT DepartmentID, Name, GroupName  
FROM Test.Department ;   
-- Test insert  
INSERT Test.Department (Name, GroupName)  
    VALUES ('Audit', 'Quality Assurance') ;  
GO  
  
-- View the result  
SELECT DepartmentID, Name, GroupName  
FROM Test.Department ;  
GO  
  
```  
  
 <span data-ttu-id="8579b-184">Les instructions [!INCLUDE[tsql](../../../includes/tsql-md.md)] qui utilisent `SELECT *` recevront la nouvelle colonne en tant que dernière colonne au lieu de première.</span><span class="sxs-lookup"><span data-stu-id="8579b-184">[!INCLUDE[tsql](../../../includes/tsql-md.md)] statements that use `SELECT *` will receive the new column as the last column instead of the first column.</span></span> <span data-ttu-id="8579b-185">Si ce n'est pas acceptable, vous devez créer une toute nouvelle table, y déplacez les données, puis y recréer les autorisations.</span><span class="sxs-lookup"><span data-stu-id="8579b-185">If this is not acceptable, then you must create an entirely new table, move the data to it, and then recreate the permissions on the new table.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="8579b-186">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="8579b-186">Related Content</span></span>  
 [<span data-ttu-id="8579b-187">CREATE SEQUENCE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8579b-187">CREATE SEQUENCE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-sequence-transact-sql)  
  
 [<span data-ttu-id="8579b-188">ALTER SEQUENCE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8579b-188">ALTER SEQUENCE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-sequence-transact-sql)  
  
 [<span data-ttu-id="8579b-189">DROP SEQUENCE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8579b-189">DROP SEQUENCE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-sequence-transact-sql)  
  
 [<span data-ttu-id="8579b-190">IDENTITY &#40;propriété&#41; &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8579b-190">IDENTITY &#40;Property&#41; &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-table-transact-sql-identity-property)  
  
  
