---
title: Inteligentne rekomendacje w aplikacji Attract
description: W tym artykule wyjaśniono, jak można wykorzystać aparat uczenia maszynowego do formułowania zaleceń dotyczących stanowisk pracy i kandydatów na stanowiska w Microsoft Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 05/16/2019
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
ms.openlocfilehash: fa06821c98e42dcd8590a764db9beb4a5c33fca2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462187"
---
# <a name="intelligent-recommendations-in-attract"></a>Inteligentne rekomendacje w aplikacji Attract

[!include [banner](includes/banner.md)]

Aparat uczenia maszynowego może pomagać osobom rekrutującym i menedżerom zatrudniającym w szybkim identyfikowaniu najlepszych kandydatów na określone stanowiska. Może także pomagać prospektom znajdować stanowiska, które najlepiej pasują do ich profilu i zainteresowań. Wraz z używaniem tych funkcji i przekazywaniem informacji zwrotnych jakość rekomendacji będzie się poprawiać.

> [!NOTE] 
> - Funkcje inteligentnych rekomendacji są dostępne tylko po zainstalowaniu [dodatku kompleksowej obsługi rekrutacji](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).
> - Funkcje wymienione w tym temacie są dostępne w ramach wydania wersji zapoznawczej. Zawartość i funkcje mogą ulec zmianie. Aby użyć tej funkcji, poproś administratora o włączenie jej za pomocą opcji **Centrum administracyjne** w Attract. Ustaw parametry **Rekomendacja kandydata**, **Rekomendacja funkcji** i **Rekomendacja prospektów** jako **Wł**. Aby uzyskać więcej informacji, zobacz [Dostęp do funkcji w wersji zapoznawczej w Microsoft Dynamics 365 Talent](./access-preview-feature.md). 


## <a name="candidate-recommendations"></a>Rekomendacje kandydatów

Ponieważ oferty pracy mogą przyciągać setki kandydatów, może być trudno osobom rekrutującym i menedżerom zatrudniającym znaleźć kandydatów, których umiejętności i ogólne przygotowanie najlepiej pasują do danego stanowiska. Mechanizm uczenia maszynowego może analizować korelację między opisem funkcji a wymaganiami oraz dane z życiorysów i profili kandydatów, i na tej podstawie sporządzać zalecenia dotyczące kandydatów. Rekomendacje kandydatów mogą pomóc osobom rekrutującym i menedżerom zatrudniającym identyfikować najlepiej rokujące osoby i szybciej przekazywać je do etapu rozmowy kwalifikacyjnej. Jeśli na którąkolwiek funkcję jest więcej niż 10 kandydatów lub prospektów mających życiorysy lub kompletne profile, to kandydaci lub prospekci najlepiej spełniający wymagania określone dla funkcji są wyświetlani w sekcji **Kandydaci do wzięcia pod uwagę** na stronie **Funkcja**.

Dla każdego polecanego kandydata można wybrać opcję **Wyświetl kandydata** na karcie kandydata, a następnie przejrzeć profil kandydata i podjąć czynności wobec jego zgłoszenia. Można użyć przycisku wielokropka (**...**), aby otworzyć profil kandydata na nowej karcie. Można także użyć przycisku wielokropka w celu przesłania opinii o rekomendacji. W ten sposób pomagasz doprecyzować działanie aparatu rekomendacji i poprawić jakość przyszłych rekomendacji. Wszystkie rekomendacje, które Ci się nie podobają, są usuwane z sekcji **Kandydaci do wzięcia pod uwagę** po odświeżeniu strony **Funkcja**. Na karcie opinii można wskazać, dlaczego uznajesz rekomendację za mało użyteczną.

## <a name="job-recommendations"></a>Rekomendacja funkcji 

Gdy potencjalny pracownik wysyła podanie o pracę z witryny rozwoju kariery, Attract rekomenduje inne wolne stanowiska w organizacji. Zalecenia te bazują na wcześniejszych zgłoszeniach oraz życiorysie lub profilu kandydata prospektu. W związku z tym rekomendacje funkcji pomagają prospektom szybko identyfikować funkcje, które najlepiej do nich pasują. Rekomendacje funkcji są przedstawiane prospektom, jeśli w witrynie rozwoju kariery są opublikowane oferty na więcej niż dziesięć funkcji. Z poziomu karty rekomendacji prospekci mogą otworzyć szczegóły oferty pracy. Mogą także przekazać swoją opinię o rekomendacji, tak aby poprawić trafność przyszłych zaleceń.

## <a name="prospect-recommendations"></a>Rekomendacja prospektów 

Gdy nowe stanowisko staje się dostępne, przeszukanie wszystkich kandydatów z przeszłości i całej sieci talentów może zająć dużo czasu. Aby aplikacja Attract mogła w tym pomóc, można używać inteligentnych algorytmów uczenia maszynowego. Oznacza to, że Attract przegląda wszystkich kandydatów i proponuje tych, którzy odpowiadają kryteriom utworzonego stanowiska. Aby wyświetlić te rekomendacje, włącz etap **prospekt** dla stanowiska. W ciągu maksymalnie minuty Attract zeskanuje całą bazę danych kandydatów i wyświetli rekomendacje.

Zalecenia są wyświetlane jako karty na karcie **prospektów** wszystkich stanowisk, które mają włączony etap **prospektu**. Te karty zawierają listy umiejętności znalezionych w profilu prospektu, jak również wszelkie informacje na temat wykształcenia. Jeśli znajdziesz odpowiednią rekomendację, możesz dodać kandydata jako prospekta na dane stanowisko.

> [!NOTE]
> Jeśli używasz aplikacji Attract od niedawna, musisz zaczekać, aż w bazie pojawi się co najmniej 10 pełnych profili lub życiorysów, aby korzystać z tej funkcji.

Aby uniknąć potencjalnych różnic w rekomendacjach, Attract skanuje tylko profile kandydatów pod kątem umiejętności, kwalifikacji i innych słów kluczowych odpowiadających opisowi stanowiska. Ponadto Attract usuwa z profilu informacje umożliwiające identyfikację kandydata przed dokonaniem oceny.
