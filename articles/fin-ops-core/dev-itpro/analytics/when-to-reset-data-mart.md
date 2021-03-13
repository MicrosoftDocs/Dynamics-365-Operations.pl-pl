---
title: Kiedy resetować składnicę danych
description: W tym temacie wymieniono okoliczności, które mogą zostać poprawione przez zresetowanie składnicy danych, i okoliczności, w których zresetowanie składnicy danych nie będzie pomocne.
author: jinniew
manager: AnnBe
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1c1524c7a1a3fbe71c51b23571996d87641cdf7e
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093219"
---
# <a name="when-to-reset-a-data-mart"></a><span data-ttu-id="847f8-103">Kiedy resetować składnicę danych</span><span class="sxs-lookup"><span data-stu-id="847f8-103">When to reset a data mart</span></span>

<span data-ttu-id="847f8-104">Resetowanie składnicy danych może być czasochłonne.</span><span class="sxs-lookup"><span data-stu-id="847f8-104">Resetting a data mart can be time consuming.</span></span> <span data-ttu-id="847f8-105">W zależności od okoliczności ta akcja może nie być potrzebnym rozwiązaniem.</span><span class="sxs-lookup"><span data-stu-id="847f8-105">Depending on the circumstances, this action may not be the solution that's needed.</span></span> <span data-ttu-id="847f8-106">W tym temacie wymieniono okoliczności, które mogą zostać poprawione przez zresetowanie składnicy danych, a także okoliczności, w których zresetowanie składnicy danych nie będzie pomocne.</span><span class="sxs-lookup"><span data-stu-id="847f8-106">This topic lists the circumstances that might be improved by resetting a data mart, as well as circumstances in which resetting your data mart is unlikely to help.</span></span>  

## <a name="when-do-you-need-to-do-a-data-mart-reset"></a><span data-ttu-id="847f8-107">Kiedy musisz zresetować składnicę danych?</span><span class="sxs-lookup"><span data-stu-id="847f8-107">When do you need to do a data mart reset?</span></span>
<span data-ttu-id="847f8-108">Przed zresetowaniem składnicy danych należy zadać sobie poniższe pytania.</span><span class="sxs-lookup"><span data-stu-id="847f8-108">Consider the following questions before resetting a data mart.</span></span> <span data-ttu-id="847f8-109">Odpowiedź Tak na jedno lub więcej pytań może wskazywać, że organizacja może skorzystać z zalet zresetowania składnicy danych.</span><span class="sxs-lookup"><span data-stu-id="847f8-109">Answering yes to one or more questions might indicate that your organization can benefit by resetting the data mart.</span></span>

- <span data-ttu-id="847f8-110">Baza danych aplikacji została przywrócona, ale baza danych składnicy danych nie.</span><span class="sxs-lookup"><span data-stu-id="847f8-110">The application database was restored, but the data mart database was not restored.</span></span>
- <span data-ttu-id="847f8-111">W okresie księgowym są niepoprawne dane, które nie są wynikiem problemu z projektem raportu.</span><span class="sxs-lookup"><span data-stu-id="847f8-111">You see incorrect data for an accounting period, which isn't the result of an issue with the report design.</span></span>
- <span data-ttu-id="847f8-112">W okresie księgowym są widoczne niepoprawne dane i rekordy są wymienione w obszarze Próby integracji na stronie **Stan integracji** w projektancie raportów (uruchom projektanta raportów i wybierz opcję **Narzędzia > Stan integracji**).</span><span class="sxs-lookup"><span data-stu-id="847f8-112">You see incorrect data for an accounting period, and records are listed under Integration attempts on the **Integration status** page in Report Designer (start the Report Designer and select **Tools > Integration status**).</span></span>
- <span data-ttu-id="847f8-113">Otwarto zdarzenie pomocy technicznej, a inżynier pomocy technicznej zlecił zresetowanie składnicy danych w ramach kroku rozwiązywania problemów.</span><span class="sxs-lookup"><span data-stu-id="847f8-113">You've opened a support incident and a support engineer has instructed you to reset the data mart as part of a troubleshooting step.</span></span>
 
## <a name="when-its-not-appropriate-to-reset-a-data-mart"></a><span data-ttu-id="847f8-114">Kiedy resetowanie składnicy danych nie jest właściwym rozwiązaniem?</span><span class="sxs-lookup"><span data-stu-id="847f8-114">When it's not appropriate to reset a data mart?</span></span>
<span data-ttu-id="847f8-115">Istnieją pewne okoliczności, w przypadku których nie zaleca się resetowania składnicy danych.</span><span class="sxs-lookup"><span data-stu-id="847f8-115">There are some circumstances when we don't recommend resetting a data mart.</span></span> <span data-ttu-id="847f8-116">Obejmują one następujące sytuacje.</span><span class="sxs-lookup"><span data-stu-id="847f8-116">These include the following.</span></span> 

- <span data-ttu-id="847f8-117">Wszystkie okoliczności, których przyczyna nie jest wymieniona w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="847f8-117">Anytime the reason isn’t listed in this topic.</span></span>
- <span data-ttu-id="847f8-118">Występują problemy z wydajnością związane z synchronizacją danych. W tym wypadku zresetowanie składnicy danych prawdopodobnie nie pomoże.</span><span class="sxs-lookup"><span data-stu-id="847f8-118">You're experiencing performance issues that are associated with a data sync. In this circumstance, resetting the data mart probably won't help.</span></span>
- <span data-ttu-id="847f8-119">Jeśli z następujących przyczyn używasz wzorca resetowania cyklicznego:</span><span class="sxs-lookup"><span data-stu-id="847f8-119">If you have a recurring reset pattern due to any of the following reasons:</span></span> 
  - <span data-ttu-id="847f8-120">**Brakujące dane** — najpierw wyeliminuj problemy z projektem raportu i problemy z synchronizacją danych. Można np. zwrócić uwagę, że mapa informacji nie została uruchomiona od czasu zaksięgowania brakujących danych.</span><span class="sxs-lookup"><span data-stu-id="847f8-120">**Missing data** - First, eliminate report design issues and data sync timing issues, for example, you observe that the fact map hasn’t run since missing data was posted.</span></span>
  - <span data-ttu-id="847f8-121">**Stan zablokowanej integracji** — jeśli integracja jest wolna lub prawdopodobnie zablokowana, zresetowanie składnicy danych prawdopodobnie nie rozwiąże problemu.</span><span class="sxs-lookup"><span data-stu-id="847f8-121">**Stuck integration state** - If the integration is slow or seems stuck, resetting the data mart is unlikely to resolve the issue.</span></span>
  - <span data-ttu-id="847f8-122">**Próby zresetowania zostały zakończone niepowodzeniem** — jeśli dokonano kilku prób zakończenia tego resetowania i z powodu brakujących danych zostały one zakończone niepowodzeniem, zalecane jest otwarcie zdarzenia pomocy technicznej i praca z inżynierem pomocy technicznej w celu przeanalizowania sytuacji przed podjęciem próby ponownego zresetowania składnicy danych.</span><span class="sxs-lookup"><span data-stu-id="847f8-122">**Attempts to reset have been unsuccessful** - If a number of attempts to complete a reset have been made, and have been unsuccessful because of missing data, we recommend opening a support incident and working with a support engineer to analyze your situation before attempting to reset the data mart again.</span></span>
  - <span data-ttu-id="847f8-123">**Nieaktualne rekordy** — nieaktualne rekordy same w sobie nie stanowią uzasadnienia resetowania składnicy danych.</span><span class="sxs-lookup"><span data-stu-id="847f8-123">**Stale records** - Stale records by themselves don't necessarily justify resetting the data mart.</span></span> <span data-ttu-id="847f8-124">Jeśli zestaw danych jest duży, proces resetowania może potrwać trochę czasu, ale może spowodować poprawę.</span><span class="sxs-lookup"><span data-stu-id="847f8-124">If you have a large data set, the reset process will take some time to run, but is unlikely to result in improvement.</span></span>
 
## <a name="what-a-data-mart-reset-does-not-do"></a><span data-ttu-id="847f8-125">Czego nie powoduje zresetowanie składnicy danych</span><span class="sxs-lookup"><span data-stu-id="847f8-125">What a data mart reset does not do</span></span>  
- <span data-ttu-id="847f8-126">Resetowanie rozpocznie się tylko po ukończeniu istniejących zadań.</span><span class="sxs-lookup"><span data-stu-id="847f8-126">A reset will only start when existing tasks are complete.</span></span> <span data-ttu-id="847f8-127">Dzięki temu stare dane nie będą wstawiane.</span><span class="sxs-lookup"><span data-stu-id="847f8-127">This ensures that old data is not inserted.</span></span> <span data-ttu-id="847f8-128">Na tym etapie może zostać wyświetlony następujący komunikat: „Resetowanie składnicy danych nie zostało przetworzone z powodu aktywnego zadania.</span><span class="sxs-lookup"><span data-stu-id="847f8-128">At this point you may see a message such as, “The data mart reset was unable to be processed because of an active task.</span></span> <span data-ttu-id="847f8-129">Spróbuj ponownie później”.</span><span class="sxs-lookup"><span data-stu-id="847f8-129">Please try again later.”</span></span>
- <span data-ttu-id="847f8-130">Zresetowanie spowoduje wyłączenie zadań integracji i usunięcie wszystkich danych składnicy.</span><span class="sxs-lookup"><span data-stu-id="847f8-130">The reset will disable the integration tasks and delete all the data mart data.</span></span> <span data-ttu-id="847f8-131">Integracja została ponownie włączona.</span><span class="sxs-lookup"><span data-stu-id="847f8-131">The integration is re-enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="847f8-132">W poniższych punktach określono dwie opcje, których zresetowanie składnicy danych *nie* spowoduje.</span><span class="sxs-lookup"><span data-stu-id="847f8-132">The following points specify two things that resetting a data mart will *not* do.</span></span> <br>
> - <span data-ttu-id="847f8-133">Resetowanie nie powoduje wyczyszczenia projektów raportów.</span><span class="sxs-lookup"><span data-stu-id="847f8-133">Resets do not clear report designs.</span></span> <br>
> - <span data-ttu-id="847f8-134">Resetowanie nie powoduje wyczyszczenia danych firmy lub użytkownika, chyba że zostaną wybrane.</span><span class="sxs-lookup"><span data-stu-id="847f8-134">Resets do not clear company data or user data unless selected.</span></span>
