---
title: Profile oceny
description: W tym temacie opisano sposób konfigurowania danych do profili stawek.
author: Henrikan
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: de5789e1b8e36fc52f308967961fe12389628209ff423e26928d1fb15395a08f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6772383"
---
# <a name="rating-profiles"></a>Profile oceny

Profil stawki przypomina umowę logistyczną (ale nie umowę prawną). Jest on używany do określenia taryf transportowych dla ładunków. 

Każdy profil stawek jest unikatowy dla przewoźnika. W profilu możesz powiązać przewoźnika z główną stawką. Główne stawki określają przypisania stawek podstawowych i stawki podstawowe. Stawka podstawowa określa stawkę przewoźnika.

Możesz skonfigurować profil stawek, korzystając z ogólnej strony, która przedstawia przegląd wszystkich istniejących profili stawek. Alternatywnie możesz skonfigurować profil stawek bezpośrednio od przewoźnika. W obu przypadkach informacje skonfigurowane dla profilu stawek są takie same.

## <a name="create-or-edit-a-rating-profile-on-the-rating-profiles-page"></a>Tworzenie lub edytowanie profilu oceny na stronie profile stawek

Na stronie **Profile stawek** można przejrzeć wszystkie dostępne profile stawek. Można również edytować istniejące profile i tworzyć nowe.

1. Przejdź do **Zarządzanie transportem \> Konfiguracja \> Stawki \> Profil stawek**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy profil stawek do siatki, lub wybierz **Edytuj**, aby edytować istniejący profil.
1. W wierszu nowego lub istniejącego profilu stawek należy określić następujące pola:

    - **Profil stawek** – Wprowadź unikatowy identyfikator (ID) profilu stawek.
    - **Nazwa** — umożliwia wprowadzenie opisowej nazwy profilu stawek.
    - **Przewoźnik** — umożliwia wybór firmy przewozowej. Profil stawek, który konfigurujesz, będzie również widoczny na stronie **Przewoźnicy** dla wybranego przewoźnika.
    - **Oddział** i **Magazyn** — umożliwia wybór oddziału i magazynu.
    - **Aparat wyznaczania stawki** — umożliwia wybór aparatu stawek dla profilu stawek.
    - **Główne stawki** — umożliwia wybór głównych stawek dla profilu stawek. Głównej stawki możesz użyć do określania typu stawki podstawowej i stawki podstawowej. Aby uzyskać więcej informacji, zobacz [Ustawianie danych głównych stawki](set-up-rate-masters.md).
    - **Aparat czasu tranzytu** — umożliwia wybór aparatu czasu tranzytu dla profilu stawek.
    - **Indeks paliwowy przewoźnika** – Wybierz indeks paliwa przewoźnika dla profilu stawek.
    - **Data i godzina rozpoczęcia wejścia w życie** oraz **Data i godzina zakończenia obowiązywania** — umożliwia zdefiniowanie okresu, w którym profil stawek powinien być aktywny.

1. Na okienku akcji wybierz opcję **Zapisz**.

## <a name="create-a-rating-profile-directly-on-the-shipping-carriers-page"></a>Tworzenie profilu stawek bezpośrednio na stronie Przewoźnicy

1. Przejdź do pozycji **Zarządzanie transportem \> Ustawienia \> Przewoźnicy \> Firmy przewozowe**.
1. Wybierz przewoźnika z listy.
1. Na skróconej karcie **Profile stawek** kliknij opcję **Nowy**, aby utworzyć profil oceny.
1. Umożliwia ustawienie pól dla nowego profilu stawek. Te pola odpowiadają polom na stronie **Profile stawek** w sposób opisany w poprzedniej sekcji tego tematu.

> [!NOTE]
> Profile utworzone na stronie **Przewoźnicy** są również wyświetlane na stronie **Profile ocen**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]