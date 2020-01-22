---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (31 stycznia 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 01/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-01-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: fbbecd4e0f205c2f09ec30548756ff1a43872644
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2019
ms.locfileid: "2899112"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-31-2019"></a><span data-ttu-id="4bd12-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (31 stycznia 2019 r.)</span><span class="sxs-lookup"><span data-stu-id="4bd12-103">What's new or changed in Dynamics 365 Talent (January 31, 2019)</span></span>

<span data-ttu-id="4bd12-104">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="4bd12-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

<span data-ttu-id="4bd12-105">**Kompilacja 8.1.2128**</span><span class="sxs-lookup"><span data-stu-id="4bd12-105">**Build 8.1.2128**</span></span>

## <a name="core-hr-changes"></a><span data-ttu-id="4bd12-106">Zmiany w Core HR</span><span class="sxs-lookup"><span data-stu-id="4bd12-106">Core HR Changes</span></span>

### <a name="time-off-taken-on-leave-people-card-doesnt-consider-leave-plan-dates"></a><span data-ttu-id="4bd12-107">Czas wolny wzięty na karcie urlopów osób nie bierze pod uwagę dat planu urlopów</span><span class="sxs-lookup"><span data-stu-id="4bd12-107">Time off taken on leave people card doesn't consider leave plan dates</span></span>
<span data-ttu-id="4bd12-108">Dla tych, które mają plany urlopów, które nie działają w roku kalendarzowym, karta **Zajęte** pokazuje teraz czas wolny wzięty w roku urlopowym zdefiniowanym w planie.</span><span class="sxs-lookup"><span data-stu-id="4bd12-108">For those that have leave plans that don’t run on a calendar year, the **Taken** card now displays time off that’s been taken in the plan-defined leave year.</span></span> <span data-ttu-id="4bd12-109">Na przykład jeśli rok urlopowy w organizacji jest od 1 czerwca do 30 maja, a pracownik wziął 3 dni urlopu w grudniu, karta **Zajęte** na dzień 15 stycznia będzie pokazywała 3 dni.</span><span class="sxs-lookup"><span data-stu-id="4bd12-109">For example, if an organization’s leave year is June 1 through May 30 and an employee has taken 3 days off in December, the **Taken** card on January 15, will display 3 days.</span></span> 

### <a name="accrual-amounts-not-matching-tier-date-basis"></a><span data-ttu-id="4bd12-110">Naliczane kwoty nie pasują do podstawy daty warstwy</span><span class="sxs-lookup"><span data-stu-id="4bd12-110">Accrual amounts not matching tier date basis</span></span>
<span data-ttu-id="4bd12-111">Nowe opcje dodano do urlopów i nieobecności (parametry **Zasoby ludzkie**) umożliwiające klientom ustalenie, kiedy obowiązują miesiące daty rozpoczęcia pracy pracowników.</span><span class="sxs-lookup"><span data-stu-id="4bd12-111">New options have been added to leave and absence (**Human resources** parameters) to enable customers to determine when employees’ months of service date are effective.</span></span> <span data-ttu-id="4bd12-112">W niektórych organizacjach ta data jest ostatnim dniem miesiąca, ale w innych może być to początek następnego miesiąca.</span><span class="sxs-lookup"><span data-stu-id="4bd12-112">For some organizations, the date is the end of the month, but for others it may be the start of the next month.</span></span> <span data-ttu-id="4bd12-113">Na przykład jedna organizacja może udzielać czasu wolnego 31 grudnia, a inna może udzielać czasu wolnego od 1 stycznia.</span><span class="sxs-lookup"><span data-stu-id="4bd12-113">For example, one organization may award time off on December 31, while another may award time off on January 1.</span></span> <span data-ttu-id="4bd12-114">Ta opcja pozwoli wybrać podczas, kiedy ma nastąpić to udzielenie.</span><span class="sxs-lookup"><span data-stu-id="4bd12-114">This option will allow you to choose when the award should occur.</span></span> 

### <a name="worker-hire-actions-are-stuck-in-workflow-complete-state"></a><span data-ttu-id="4bd12-115">Działania związane z zatrudnieniem pracownika utknęły w stanie „Przepływ pracy zakończony”</span><span class="sxs-lookup"><span data-stu-id="4bd12-115">Worker hire actions are stuck in "Workflow complete" state</span></span>
<span data-ttu-id="4bd12-116">Wprowadzono zmiany, aby rozwiązać problem polegający na tym, że niewielka liczba przepływów pracy kończyła się stanem „Przepływ pracy zakończony”.</span><span class="sxs-lookup"><span data-stu-id="4bd12-116">Changes have been made to correct an issue where a small number of workflows finished with a "Workflow complete" status.</span></span> <span data-ttu-id="4bd12-117">Nowe przepływy pracy powinny teraz przechodzić do stanu „Ukończony” po zakończeniu przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="4bd12-117">New workflows should now move to a "Completed" state when the workflow finishes.</span></span> <span data-ttu-id="4bd12-118">Wszystkie przepływy pracy w stanie ukończenia przepływu pracy zostaną przełączone w stan błędu, który pozwoli na ich zaktualizowanie lub usunięcie, w zależności od potrzeb.</span><span class="sxs-lookup"><span data-stu-id="4bd12-118">Any workflows in a workflow completed status will be transitioned to an error status to allow for updating or removal if required.</span></span> 
