---
title: Sprawdzanie spójności transakcji w rozwiązaniu Retail
description: W tym temacie opisano funkcje sprawdzania spójności transakcji sprzedaży detalicznej w rozwiązaniu Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 01/08/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: db01a12b92574b41f1f4fe7281c23992e0d36027
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "302751"
---
# <a name="retail-transaction-consistency-checker"></a><span data-ttu-id="e49d7-103">Sprawdzanie spójności transakcji w rozwiązaniu Retail</span><span class="sxs-lookup"><span data-stu-id="e49d7-103">Retail transaction consistency checker</span></span>


[!include [banner](includes/banner.md)]
[!include [preview banner](includes/preview-banner.md)]

<span data-ttu-id="e49d7-104">W tym temacie opisano funkcje sprawdzania spójności transakcji sprzedaży detalicznej wprowadzone w rozwiązaniu Microsoft Dynamics 365 for Finance and Operations (wersja 8.1.3).</span><span class="sxs-lookup"><span data-stu-id="e49d7-104">This topic describes the retail transaction consistency checker functionality introduced in Microsoft Dynamics 365 for Finance and Operations version 8.1.3.</span></span> <span data-ttu-id="e49d7-105">Sprawdzanie spójności pozwala zidentyfikować i odizolować niespójne transakcji przed ich pobraniem przez proces księgowania zestawienia.</span><span class="sxs-lookup"><span data-stu-id="e49d7-105">The consistency checker identifies and isolates inconsistent transactions before they are picked up by the statement posting process.</span></span>

<span data-ttu-id="e49d7-106">Po zaksięgowaniu zestawienia w rozwiązaniu Retail funkcja księgowania może zakończyć się niepowodzeniem z powodu niespójności danych w tabelach transakcji sprzedaży detalicznej.</span><span class="sxs-lookup"><span data-stu-id="e49d7-106">When a statement is posted in Retail, posting can fail due to inconsistent data in the retail transaction tables.</span></span> <span data-ttu-id="e49d7-107">Przyczyną tego problemu z danymi mogą być nieprzewidziane problemy w aplikacji punktu sprzedaży (POS) lub jeśli transakcje zostały nieprawidłowo zaimportowane z innych systemów POS.</span><span class="sxs-lookup"><span data-stu-id="e49d7-107">The data issue may be caused by by unforeseen issues in the point of sale (POS) application, or if transactions were incorrectly imported from third-party POS systems.</span></span> <span data-ttu-id="e49d7-108">Przykłady wyświetlania tych niespójności:</span><span class="sxs-lookup"><span data-stu-id="e49d7-108">Examples of how these inconsistencies may appear include:</span></span> 

  - <span data-ttu-id="e49d7-109">Suma transakcji w tabeli nagłówka jest niezgodna z łączną wartością transakcji w wierszach.</span><span class="sxs-lookup"><span data-stu-id="e49d7-109">The transaction total on the header table does not match the transaction total on the lines.</span></span>
  - <span data-ttu-id="e49d7-110">Liczba wierszy w tabeli nagłówka jest niezgodna z liczbą wierszy w tabeli transakcji.</span><span class="sxs-lookup"><span data-stu-id="e49d7-110">The line count on the header table does not match with the number of lines in the transaction table.</span></span>
  - <span data-ttu-id="e49d7-111">Podatki w tabeli nagłówka są niezgodne z kwotą podatku w wierszach.</span><span class="sxs-lookup"><span data-stu-id="e49d7-111">Taxes on the header table do not match the tax amount on the lines.</span></span> 
  
<span data-ttu-id="e49d7-112">Kiedy niezgodne transakcje są pobierane przez proces księgowania zestawienia, powstają niespójne faktury sprzedaży i dzienniki płatności i w efekcie cały proces księgowania zestawienia kończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="e49d7-112">When inconsistent transactions are picked up by the statement posting process, inconsistent sales invoices and payment journals are created, and the entire statement posting process fails as a result.</span></span> <span data-ttu-id="e49d7-113">Odzyskiwanie zestawień w tym stanie wymaga skomplikowanych poprawek danych w wielu tabelach transakcji.</span><span class="sxs-lookup"><span data-stu-id="e49d7-113">Recovering the statements from such a state involves complex data fixes across multiple transaction tables.</span></span> <span data-ttu-id="e49d7-114">Kontroler spójności transakcji sprzedaży detalicznej zapobiega takim problemom.</span><span class="sxs-lookup"><span data-stu-id="e49d7-114">The retail transaction consistency checker prevents such issues.</span></span>

<span data-ttu-id="e49d7-115">Wykres poniżej pokazuje proces księgowania z kontrolerem spójności transakcji.</span><span class="sxs-lookup"><span data-stu-id="e49d7-115">The following chart illustrates the posting process with the transaction consistency checker.</span></span>

<span data-ttu-id="e49d7-116">![Proces księgowania zestawień z kontrolerem spójności transakcji sprzedaży detalicznej](./media/validchecker.png "Proces księgowania zestawień z kontrolerem spójności transakcji sprzedaży detalicznej")</span><span class="sxs-lookup"><span data-stu-id="e49d7-116">![Statement posting process with retail transaction consistency checker](./media/validchecker.png "Statement posting process with retail transsaction consistency checker")</span></span>

<span data-ttu-id="e49d7-117">Zadanie wsadowe **Sprawdź poprawność transakcji w sklepie** sprawdza spójność tabel transakcji sprzedaży detalicznej w następujących scenariuszach.</span><span class="sxs-lookup"><span data-stu-id="e49d7-117">The **Validate store transactions** batch process checks the consistency of the retail transaction tables for the following scenarios.</span></span>

- <span data-ttu-id="e49d7-118">Konto odbiorcy — sprawdza, czy konto odbiorcy w tabelach transakcji sprzedaży detalicznej istnieje w danych głównej odbiorcy w centrali.</span><span class="sxs-lookup"><span data-stu-id="e49d7-118">Customer account - Validates that the customer account in the retail transaction tables exists in the HQ customer master.</span></span>
- <span data-ttu-id="e49d7-119">Liczba wierszy — sprawdza, czy liczba wierszy w tabeli nagłówka transakcji jest zgodna z liczbą wierszy w tabelach transakcji sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="e49d7-119">Line count - Validates that the number of lines, as captured on the transaction header table, matches the number of lines in the sales transaction tables.</span></span>

## <a name="set-up-the-consistency-checker"></a><span data-ttu-id="e49d7-120">Konfigurowanie modułu sprawdzania spójności</span><span class="sxs-lookup"><span data-stu-id="e49d7-120">Set up the consistency checker</span></span>
<span data-ttu-id="e49d7-121">Skonfiguruj proces wsadowy „Sprawdź poprawność transakcji w sklepie” na **Handel detaliczny \> Składniki IT w handlu detalicznym \> Księgowanie w punkcie sprzedaży**, dla okresowych zadań.</span><span class="sxs-lookup"><span data-stu-id="e49d7-121">Configure the "Validate store transactions" batch process, at **Retail \> Retail IT \> POS posting**, for periodic runs.</span></span> <span data-ttu-id="e49d7-122">Zadanie wsadowe można zaplanować według hierarchii organizacyjnej sklepu w sposób podobny do tego, w jaki skonfigurowane są procesy „Oblicz zestawienie w trybie wsadowym” i „Księgowanie zestawienia w trybie wsadowym”.</span><span class="sxs-lookup"><span data-stu-id="e49d7-122">The batch job can be scheduled based on store organization hierarchy, similar to how the "Calculate statement in batch" and "Post statement in batch" processes are set up.</span></span> <span data-ttu-id="e49d7-123">Zalecamy skonfigurowanie tego procesu w taki sposób, aby uruchamiał się wiele razy w ciągu dnia i każdorazowo po wykonaniu zadania ściągania.</span><span class="sxs-lookup"><span data-stu-id="e49d7-123">We recommend that you configure this batch process to run multiple times in a day and schedule it so that it runs at the end of every P-job execution.</span></span>

## <a name="results-of-validation-process"></a><span data-ttu-id="e49d7-124">Wyniki procesu sprawdzania</span><span class="sxs-lookup"><span data-stu-id="e49d7-124">Results of validation process</span></span>
<span data-ttu-id="e49d7-125">Wyniki sprawdzania przez proces wsadowy są zaznaczone na odpowiedniej transakcji sprzedaży detalicznych.</span><span class="sxs-lookup"><span data-stu-id="e49d7-125">The results of the validation check by the batch process are tagged on the appropriate retail transaction.</span></span> <span data-ttu-id="e49d7-126">Pole **Stan weryfikacji** w rekordzie transakcji sprzedaży detalicznej ma wartość **Powodzenie** lub **Błąd**, a data ostatniej weryfikacji znajduje się w polu **Godzina ostatniej weryfikacji**.</span><span class="sxs-lookup"><span data-stu-id="e49d7-126">The **Validation status** field on the retail transaction record is either set to **Successful** or **Error**, and the date of the last validation run appears on the **Last validation time** field.</span></span>

<span data-ttu-id="e49d7-127">Aby wyświetlić dłuższy opis błędu sprawdzania poprawności, zaznacz odpowiedni rekord transakcji sklepu i kliknij przycisk **Błędy weryfikacji**.</span><span class="sxs-lookup"><span data-stu-id="e49d7-127">To view more descriptive error text relating to a validation failure, select the relevant retail store transaction record and click the **Validation errors** button.</span></span>

<span data-ttu-id="e49d7-128">Transakcje, które nie przeszły weryfikacji, oraz transakcji, które nie zostały jeszcze zweryfikowane, nie będą pobierane do zestawień.</span><span class="sxs-lookup"><span data-stu-id="e49d7-128">Transactions that fail the validation check and transactions that have not yet been validated will not be pulled into statements.</span></span> <span data-ttu-id="e49d7-129">W trakcie procesu „Oblicz zestawienie” użytkownicy otrzymają powiadomienie, że istnieją transakcje, które mogły zostać uwzględnione w zestawieniu, ale tak się nie stało.</span><span class="sxs-lookup"><span data-stu-id="e49d7-129">During the "Calculate statement" process, users will be notified if there are transactions that could have been included in the statement but weren't.</span></span>

<span data-ttu-id="e49d7-130">W przypadku wystąpienia błędu weryfikacji można wyeliminować tylko po skontaktowaniu się z Pomocą techniczną firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e49d7-130">If a validation error is found, the only way to fix the error is to contact Microsoft Support.</span></span> <span data-ttu-id="e49d7-131">W przyszłej wersji zostanie dodana funkcja pozwalająca użytkownikom naprawiać rekordy z błędami za pomocą interfejsu.</span><span class="sxs-lookup"><span data-stu-id="e49d7-131">In a future release, capability will be added so that users can fix the records that failed through the user interface.</span></span> <span data-ttu-id="e49d7-132">Zostaną również dodane funkcje rejestrowania i inspekcji pozwalające śledzić historię modyfikacji.</span><span class="sxs-lookup"><span data-stu-id="e49d7-132">Logging and auditing capabilities will also be made available to trace the history of the modifications.</span></span>

> [!NOTE]
> <span data-ttu-id="e49d7-133">Oprócz tego w przyszłej wersji pojawią się też dodatkowe reguły weryfikacji dostosowane do innych scenariuszy.</span><span class="sxs-lookup"><span data-stu-id="e49d7-133">Additional validation rules to support more scenarios will be added in a future release.</span></span>
