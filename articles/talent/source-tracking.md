---
title: Śledzenie źródeł profilów i zgłoszeń kandydatów
description: Ten temat zawiera informacje dotyczące śledzenia źródła dla profili kandydata i zgłoszeń.
author: hachandr
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 5b368e97a716cd1ce4f668c2a97326877a2d3dff
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551894"
---
# <a name="track-sources-for-candidate-profiles-and-applications"></a>Śledzenie źródeł profilów i zgłoszeń kandydatów

[!include[banner](../includes/banner.md)]

> [!NOTE] 
> Funkcje wymienione w tym temacie są dostępne w ramach wydania wersji zapoznawczej. Zawartość i funkcje mogą ulec zmianie. Aby użyć tej funkcji, poproś administratora o włączenie jej za pomocą **ustawień administratora** w Attract. W przyszłej wersji będą dostępne raporty ze śledzenia źródła. Aby uzyskać więcej informacji, zobacz [Dostęp do funkcji w wersji zapoznawczej w aplikacji Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).

Gdy kandydaci zgłaszają się do pracy na stanowisku, Attract automatycznie śledzi źródła ich aplikacji, zapewniając cenne informacje, które pomagają w procesie rekrutacji. Osoby prowadzące rekrutację i menedżerowie zatrudniający mogą także wybrać źródła aplikacji, dodając ręcznie kandydata do stanowiska lub puli umiejętności i kandydatów.

Można wyświetlić źródło aplikacji w szczegółach działań aplikacji na karcie **działania**, a także w historii aplikacji w obszarze **profilu** w pulach umiejętności i kandydatów. Można znaleźć źródło profilu kandydata w szczegółach kandydata na karcie **profil** zarówno w aplikacjach, jak i pulach umiejętności i kandydatów.

> [!NOTE] 
> Szablony procesów są dostępne po zainstalowaniu [dodatku kompleksowej obsługi rekrutacji](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).

## <a name="pre-configured-sources"></a>Wstępnie skonfigurowane źródła

Domyślna lista źródeł zawiera wspólne źródła aplikacji. Niektóre typy źródeł, takie jak **Tablica funkcji** i **Sieć społecznościowa** mają dodatkowe szczegóły źródeł. Na przykład **sieć społecznościowa** obejmuje witryny, takie jak Facebook i Twitter. Typ źródła **Polecenie** umożliwia określenie pracownika wewnętrznego jako osoby polecającej. Domyślna lista źródeł zawiera następujące wstępnie skonfigurowane źródła:

-   Witryna kariery Attract

-   Agencja

-   Targi kariery

-   Dział marketingu firmy

-   Wystawy i konferencje handlowe

-   Stowarzyszenia branżowe

-   Tablica funkcji

    -   Indeed

    -   Seek

    -   CareerBuilder

    -   Google Jobs

    -   Xing

    -   Glassdoor

    -   Monster Jobs

-   Magazyny i publikacje

-   Sieci społecznościowe

    -   Facebook

    -   Twitter

-   Rekrutacja na uniwersytetach

-   LinkedIn

-   Zastrzeżone

-   Polecenie

-   Dodany przez osobę rekrutującą

-   Inna

## <a name="customize-the-source-list"></a>Dostosowywanie listy źródłowej 

Można rozszerzyć listy źródłowe, aby uwzględnić dodatkowe źródła aplikacji. Aby dostosować tę listę, postępuj zgodnie z instrukcjami w [Rozszerzanie zestawów opcji w Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/extensibility-attract#extending-option-sets-in-attract). Edytuj jednostkę **źródła talentu**, aby uwzględnić dodatkowe źródła. 

Aby uniknąć negatywnych skutków w interfejsie użytkownika, nie edytuj i nie usuwaj wartości wyliczanych atrybutu **kategoria talentu** (nie nazw) dla następujących pozycji:

- **Polecenie**
- **LinkedIn**
- **Inna**

Zamiast tego można rozszerzyć wyliczenia **źródła talentu**, aby dodać inne typy źródeł.
