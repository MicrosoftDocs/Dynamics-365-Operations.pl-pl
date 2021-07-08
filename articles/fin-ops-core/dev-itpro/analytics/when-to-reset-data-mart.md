---
title: Resetowanie składnicy danych FAQ
description: Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące resetowania składnicy danych.
author: jinniew
ms.date: 06/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-05-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 7cd96c7bc698986ef1ef07ca88479a3d49f22924
ms.sourcegitcommit: ecabf43282a3e55f1db40341aa3f3c7950b9e94c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/16/2021
ms.locfileid: "6266616"
---
# <a name="data-mart-resets-faq"></a><span data-ttu-id="e5ce5-103">Resetowanie składnicy danych FAQ</span><span class="sxs-lookup"><span data-stu-id="e5ce5-103">Data mart resets FAQ</span></span>

<span data-ttu-id="e5ce5-104">Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące resetowania składnicy danych.</span><span class="sxs-lookup"><span data-stu-id="e5ce5-104">This topic provides answers to some frequently asked questions about data mart resets.</span></span> <span data-ttu-id="e5ce5-105">Zresetowanie składnicy danych może być procesem czasochłonnym i w zależności od okoliczności może nie być rozwiązaniem, które jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="e5ce5-105">A reset of the data mart can be a time-consuming process and, depending on the circumstances, might not be the solution that is required.</span></span> <span data-ttu-id="e5ce5-106">Dlatego ten temat zawiera informacje o okolicznościach, w których reset składnicy danych może pomóc, a także o okolicznościach, w których jest to mało prawdopodobne.</span><span class="sxs-lookup"><span data-stu-id="e5ce5-106">Therefore, this topic includes information about circumstances where a data mart reset might help and also circumstances where it's unlikely to help.</span></span>

## <a name="what-is-a-data-mart-reset"></a><span data-ttu-id="e5ce5-107">Co to jest reset zbiorczej bazy danych?</span><span class="sxs-lookup"><span data-stu-id="e5ce5-107">What is a data mart reset?</span></span>

<span data-ttu-id="e5ce5-108">Reset składnicy danych wyłączy zadania integracji, usunie wszystkie dane składnicy danych, a następnie ponownie włączy integrację.</span><span class="sxs-lookup"><span data-stu-id="e5ce5-108">A data mart reset will disable the integration tasks, delete all the data mart data, and then re-enable integration.</span></span>

<span data-ttu-id="e5ce5-109">Aby zapewnić, że stare dane nie zostaną wstawione, reset składnicy danych może zostać uruchomiony dopiero po zakończeniu istniejących zadań.</span><span class="sxs-lookup"><span data-stu-id="e5ce5-109">To ensure that old data isn't inserted, a data mart reset can be started only after existing tasks are completed.</span></span> <span data-ttu-id="e5ce5-110">W przypadku próby zresetowania składnicy danych przed wykonaniem wszystkich zadań może zostać wyświetlony komunikat o następującej treści: „Resetowanie danych nie zostało przetworzone z powodu aktywnego zadania.</span><span class="sxs-lookup"><span data-stu-id="e5ce5-110">If you try to reset the data mart before all tasks are completed, you might receive a message such as, "The data mart reset was unable to be processed because of an active task.</span></span> <span data-ttu-id="e5ce5-111">Spróbuj ponownie później”.</span><span class="sxs-lookup"><span data-stu-id="e5ce5-111">Please try again later."</span></span>

## <a name="when-do-i-have-to-do-a-data-mart-reset"></a><span data-ttu-id="e5ce5-112">Kiedy mogę zresetować składnicę danych?</span><span class="sxs-lookup"><span data-stu-id="e5ce5-112">When do I have to do a data mart reset?</span></span>

<span data-ttu-id="e5ce5-113">Jeśli do danej sytuacji ma zastosowanie co najmniej jedno z następujących sprawozdań, organizacja może skorzystać z resetowania danych:</span><span class="sxs-lookup"><span data-stu-id="e5ce5-113">If one or more of the following statements apply to your situation, your organization can benefit from a data mart reset:</span></span>

- <span data-ttu-id="e5ce5-114">Baza danych aplikacji została przywrócona.</span><span class="sxs-lookup"><span data-stu-id="e5ce5-114">The application database was restored.</span></span>
- <span data-ttu-id="e5ce5-115">Otworzyłeś zgłoszenie do działu wsparcia technicznego, a inżynier działu wsparcia technicznego polecił Ci zresetować składnicę danych w ramach rozwiązywania problemów.</span><span class="sxs-lookup"><span data-stu-id="e5ce5-115">You opened a support ticket, and a Support engineer instructed you to reset the data mart as part of a troubleshooting step.</span></span>
 
## <a name="when-is-a-data-mart-reset-inappropriate"></a><span data-ttu-id="e5ce5-116">Kiedy nie resetować składnicy danych?</span><span class="sxs-lookup"><span data-stu-id="e5ce5-116">When is a data mart reset inappropriate?</span></span>

<span data-ttu-id="e5ce5-117">Oto kilka okoliczności, w których nie zalecamy resetowania:</span><span class="sxs-lookup"><span data-stu-id="e5ce5-117">Here are some of the circumstances where we don't recommend that you reset the data mart:</span></span>

- <span data-ttu-id="e5ce5-118">Występują problemy z wydajnością związane z synchronizacją.</span><span class="sxs-lookup"><span data-stu-id="e5ce5-118">You're experiencing performance issues that are associated with data synchronization.</span></span>
- <span data-ttu-id="e5ce5-119">Jeśli z następujących przyczyn używasz wzorca resetowania cyklicznego:</span><span class="sxs-lookup"><span data-stu-id="e5ce5-119">You have a recurring reset pattern for any of the following reasons:</span></span>

    - <span data-ttu-id="e5ce5-120">**Brakujące dane** – Jeśli zauważysz, że brakuje danych, otwórz zgłoszenie do pomocy technicznej w firmie Microsoft, aby sprawdzić format raportu i ewentualne problemy z synchronizacją danych.</span><span class="sxs-lookup"><span data-stu-id="e5ce5-120">**Missing data** – If you notice that data is missing, open a support ticket with Microsoft to review your report format and possible data synchronization issues.</span></span>
    - <span data-ttu-id="e5ce5-121">**Stan integracji zatrzymany**</span><span class="sxs-lookup"><span data-stu-id="e5ce5-121">**Stuck integration state**</span></span>
    - <span data-ttu-id="e5ce5-122">**Nieaktualne rekordy** — nieaktualne rekordy same w sobie nie stanowią uzasadnienia resetowania składnicy danych.</span><span class="sxs-lookup"><span data-stu-id="e5ce5-122">**Stale records** – Stale records by themselves don't necessarily justify a data mart reset.</span></span> <span data-ttu-id="e5ce5-123">Jeśli zestaw danych jest duży, proces resetowania może potrwać trochę czasu, ale raczej mało prawdopodobne jest, że może spowodować poprawę.</span><span class="sxs-lookup"><span data-stu-id="e5ce5-123">If you have a large data set, the reset process will take some time to run but is unlikely to lead to any improvement.</span></span>

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a><span data-ttu-id="e5ce5-124">Czy zresetowanie danych spowoduje utratę raportów, które już zaprojektowano?</span><span class="sxs-lookup"><span data-stu-id="e5ce5-124">If I reset the data mart, will I lose reports that I've already designed?</span></span>

<span data-ttu-id="e5ce5-125">Nr</span><span class="sxs-lookup"><span data-stu-id="e5ce5-125">No.</span></span> <span data-ttu-id="e5ce5-126">Twoje raporty są przechowywane w tabelach SQL, które nie są dotknięte przez reset składnicy danych.</span><span class="sxs-lookup"><span data-stu-id="e5ce5-126">Your reports are stored in SQL tables that aren't affected by a data mart reset.</span></span> <span data-ttu-id="e5ce5-127">Jeśli chcesz przegrać wszystkie zaprojektowane raporty, możesz utworzyć kopię zapasową projektów, które nie chcesz utracić.</span><span class="sxs-lookup"><span data-stu-id="e5ce5-127">If you're concerned about losing reports that you've designed, you can back up the designs that you don't want to lose.</span></span> <span data-ttu-id="e5ce5-128">Aby utworzyć kopię zapasową projektu, otwórz Kreator raportów i przejdź do **Firma \> Firmy \> Bloki konstrukcyjne \> Eksport**.</span><span class="sxs-lookup"><span data-stu-id="e5ce5-128">To back up designs, open Report Designer, and go to **Company \> Companies \> Building Blocks \> Export**.</span></span>
 
## <a name="do-all-users-have-to-exit-the-system-before-i-can-reset-the-data-mart"></a><span data-ttu-id="e5ce5-129">Czy wszyscy użytkownicy muszą opuścić system zanim będę mógł zresetować składnicę danych?</span><span class="sxs-lookup"><span data-stu-id="e5ce5-129">Do all users have to exit the system before I can reset the data mart?</span></span>

<span data-ttu-id="e5ce5-130">Nr</span><span class="sxs-lookup"><span data-stu-id="e5ce5-130">No.</span></span> <span data-ttu-id="e5ce5-131">Użytkownicy mogą kontynuować pracę w systemie podczas resetowania danych.</span><span class="sxs-lookup"><span data-stu-id="e5ce5-131">Users can continue to work in the system during a data mart reset.</span></span> <span data-ttu-id="e5ce5-132">Jednak do czasu zakończenia resetowania użytkownicy nie będą mieli dostępu do raportów, które zostały utworzone przy użyciu Financial Reporter.</span><span class="sxs-lookup"><span data-stu-id="e5ce5-132">However, until the reset is completed, users won't be able to access any reports that were created by using Financial Reporter.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
