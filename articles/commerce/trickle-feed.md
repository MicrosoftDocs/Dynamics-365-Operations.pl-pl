---
title: Tworzenie zamówień na podstawie cząstkowego kanału informacyjnego dla transakcji w sklepach sieci sprzedaży
description: Ten temat opisuje tworzenie zamówień na podstawie cząstkowego kanału informacyjnego dla transakcji w sklepach w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 09/04/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 0fdb1f636183e8365729ab8947a50614a77eaeac
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211052"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions"></a><span data-ttu-id="784c0-103">Tworzenie zamówień na podstawie cząstkowego kanału informacyjnego dla transakcji w sklepach sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="784c0-103">Trickle feed-based order creation for retail store transactions</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="784c0-104">W wersji 10.0.4 lub wcześniejszej rozwiązania Dynamics 365 Retail księgowanie zestawień jest operacją na koniec dnia i wszystkie transakcje są księgowane w księgach na koniec dnia.</span><span class="sxs-lookup"><span data-stu-id="784c0-104">In Dynamics 365 Retail versions 10.0.4 and earlier, statement posting is an end-of-day operation and all transactions are posted in the books at the end of the day.</span></span> <span data-ttu-id="784c0-105">Duże transakcje muszą być następnie przetworzone w ciągu krótkiego okresu, czasami powodując niepowodzenie ładowania, blokowania i księgowania zestawień.</span><span class="sxs-lookup"><span data-stu-id="784c0-105">Large transactions must then be processed in a limited time window, sometimes resulting in load and locks and statement posting failures.</span></span> <span data-ttu-id="784c0-106">Sprzedawcy detaliczni nie mogą także rozpoznać przychodu i płatności w swoich księgach w ciągu dnia.</span><span class="sxs-lookup"><span data-stu-id="784c0-106">Retailers also can't recognize revenue and payments in their books throughout the day.</span></span>

<span data-ttu-id="784c0-107">Dzięki tworzeniu zamówień na podstawie cząstkowego kanału informacyjnego wprowadzonego w wersji 10.0.5 rozwiązania Retail transakcje są przetwarzane w ciągu dnia i dopiero na koniec dnia przetwarzane są uzgodnienia finansowe metod płatności oraz inne transakcje zarządzania gotówką.</span><span class="sxs-lookup"><span data-stu-id="784c0-107">With trickle feed-based order creation introduced in Retail version 10.0.5, transactions are processed throughout the day, and only the financial reconciliation of tenders and other cash management transactions are processed at the end of the day.</span></span> <span data-ttu-id="784c0-108">Funkcja ta rozkłada obciążenie pracą podczas tworzenia zamówień sprzedaży, faktur i płatności w ciągu dnia, oferując poprawioną wydajność i zdolność rozpoznania przychodu i płatności w księgach niemal w czasie rzeczywistym.</span><span class="sxs-lookup"><span data-stu-id="784c0-108">This functionality splits the load of creating sales orders, invoices, and payments throughout the day, providing better perceived performance and the ability to recognize revenue and payments in the books in near real-time.</span></span> 


## <a name="how-to-use-trickle-feed-based-posting"></a><span data-ttu-id="784c0-109">Jak korzystać z księgowania na podstawie cząstkowego kanału informacyjnego</span><span class="sxs-lookup"><span data-stu-id="784c0-109">How to use trickle feed-based posting</span></span>
  
1. <span data-ttu-id="784c0-110">Aby włączyć księgowanie na podstawie cząstkowego kanału informacyjnego transakcji sieci sprzedaży, włącz funkcję o nazwie **Zestawienia sieci sprzedaży — cząstkowy kanał informacyjny** za pomocą opcji zarządzania funkcjami.</span><span class="sxs-lookup"><span data-stu-id="784c0-110">To enable trickle feed-based posting of retail transactions, enable the feature named **Retail statements - Trickle feed** using Feature management.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="784c0-111">Przed włączeniem tej funkcji upewnij się, że brak oczekujących na zaksięgowanie zestawień.</span><span class="sxs-lookup"><span data-stu-id="784c0-111">Before you enable the feature, make sure that no pending statements are waiting to be posted.</span></span>

2. <span data-ttu-id="784c0-112">Bieżący dokument zestawienia będzie podzielony na dwa różne typy: zestawienie transakcyjne i sprawozdanie finansowe.</span><span class="sxs-lookup"><span data-stu-id="784c0-112">The current statement document will be split into two types: transactional statement and financial statement.</span></span>

      - <span data-ttu-id="784c0-113">Zestawienie transakcyjne pobierze wszystkie niezaksięgowane i zweryfikowane transakcje i utworzy arkusze zamówień sprzedaży, faktur sprzedaży, płatności i rabatów oraz transakcje przychodu/wydatku według skonfigurowanej przez użytkownika częstotliwości.</span><span class="sxs-lookup"><span data-stu-id="784c0-113">The transactional statement will pick up all unposted and validated transactions and create sales orders, sales invoices, payment and discount journals, and income-expense transactions at the cadence that you configure.</span></span> <span data-ttu-id="784c0-114">Proces ten powinien być skonfigurowany tak, by występować jak najczęściej, aby dokumenty były tworzone, gdy transakcje są przesyłane do centrali za pomocą zadania ściągania.</span><span class="sxs-lookup"><span data-stu-id="784c0-114">You should configure this process to run at a high frequency so that documents are created when the transactions are uploaded into Headquarters through the P-job.</span></span> <span data-ttu-id="784c0-115">Gdy zestawienie transakcyjne od razu tworzy zamówienia sprzedaży i faktury sprzedaży, nie ma potrzeby konfiguracji zadań wsadowych **Zaksięguj magazyn**.</span><span class="sxs-lookup"><span data-stu-id="784c0-115">With the transactional statement that already creates sales orders and sales invoices, there is no real need to configure the **Post inventory** batch job.</span></span> <span data-ttu-id="784c0-116">Jednakże ciągle można użyć ich do spełnienia konkretnych wymagań biznesowych użytkownika.</span><span class="sxs-lookup"><span data-stu-id="784c0-116">However, you can still use it to meet specific business requirements that you may have.</span></span>  
      
     - <span data-ttu-id="784c0-117">Sprawozdanie finansowe będzie tworzone na koniec dnia i obsługuje tylko metodę zamknięcia **Zmiana**.</span><span class="sxs-lookup"><span data-stu-id="784c0-117">The financial statement is designed to be created at the end of the day and only supports the closing method of **Shift**.</span></span> <span data-ttu-id="784c0-118">To sprawozdanie będzie ograniczone do uzgodnienia finansowego i będzie tylko tworzyć arkusze dla różnic w kwotach między kwotą zliczoną i kwotą transakcji dla różnych metod płatności wraz z arkuszami dla innych transakcji zarządzania gotówką.</span><span class="sxs-lookup"><span data-stu-id="784c0-118">This statement will be limited to financial reconciliation and will only create the journals for the difference amounts between counted amount and transaction amount for the different tenders, along with journals for other cash management transactions.</span></span>   

3. <span data-ttu-id="784c0-119">Aby obliczyć zestawienie transakcyjne, przejdź do **Retail i Commerce > Retail i Commerce — składniki IT > Księgowanie w punkcie sprzedaży > Oblicz zestawienia transakcyjne w partii**.</span><span class="sxs-lookup"><span data-stu-id="784c0-119">To calculate the transactional statement, go to **Retail and Commerce > Retail and Commerce IT > POS Posting > Calculate transactional statements in batch**.</span></span> <span data-ttu-id="784c0-120">Aby zaksięgować zestawienia zestawień transakcyjnych w partii, przejdź do **Retail i Commerce > Retail i Commerce — składniki IT > Księgowanie w punkcie sprzedaży > Księguj zestawienia transakcyjne w partii**.</span><span class="sxs-lookup"><span data-stu-id="784c0-120">To post the transactional statements in batch, go to **Retail and Commerce > Retail and Commerce IT > POS Posting > Post transactional statements in batch**.</span></span>

4. <span data-ttu-id="784c0-121">Aby obliczyć zestawienie finansowe, przejdź do **Retail i Commerce > Retail i Commerce — składniki IT > Księgowanie w punkcie sprzedaży > Oblicz zestawienia finansowe w partii**.</span><span class="sxs-lookup"><span data-stu-id="784c0-121">To calculate the financial statement, go to **Retail and Commerce > Retail and Commerce IT > POS Posting > Calculate financial statements in batch**.</span></span> <span data-ttu-id="784c0-122">Aby zaksięgować zestawienia finansowe w partii, przejdź do **Retail i Commerce > Retail i Commerce — składniki IT > Księgowanie w punkcie sprzedaży > Zaksięguj zestawienia finansowe w partii**.</span><span class="sxs-lookup"><span data-stu-id="784c0-122">To post the financial statements in batch, go to **Retail and Commerce > Retail and Commerce IT > POS Posting > Post financial statements in batch**.</span></span>

> [!NOTE]
> <span data-ttu-id="784c0-123">Elementy menu **Retail i Commerce > Retail i Commerce — składniki IT > Księgowanie w punkcie sprzedaży > Oblicz zestawienia w partii** i **Retail i Commerce > Retail i Commerce — składniki IT > Księgowanie w punkcie sprzedaży > Księguj zestawienia w partii** zostały w tej nowej funkcji usunięte.</span><span class="sxs-lookup"><span data-stu-id="784c0-123">The menu items **Retail and Commerce > Retail and Commerce IT > POS Posting > Calculate statements in batch** and **Retail and Commerce > Retail and Commerce IT > POS Posting > Post statements in batch** are removed with this new feature.</span></span>

<span data-ttu-id="784c0-124">Typy zestawień transakcyjnych i sprawozdań finansowych mogą też być tworzone ręcznie.</span><span class="sxs-lookup"><span data-stu-id="784c0-124">Alternately, transactional and financial statement types can be created manually.</span></span> <span data-ttu-id="784c0-125">Przejdź do **Retail i Commerce > Kanały > Sklepy** i kliknij pozycję **Zestawienia**.</span><span class="sxs-lookup"><span data-stu-id="784c0-125">Go to **Retail and Commerce > Channels > Stores** and click **Statements**.</span></span> <span data-ttu-id="784c0-126">Kliknij **Nowe**, a następnie wybierz typ zestawienia, które chcesz utworzyć.</span><span class="sxs-lookup"><span data-stu-id="784c0-126">Click **New** and then choose the type of statement that you want to create.</span></span> <span data-ttu-id="784c0-127">Pola na stronie **Zestawienia** i akcje pod **Grupa zestawień** strony wyświetlą odpowiednie dane i akcje na podstawie wybranego typu zestawienia.</span><span class="sxs-lookup"><span data-stu-id="784c0-127">Fields on the **Statements** page and actions under the **Statement group** of the page will show relevant data and actions based on the selected statement type.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]