---
title: Arkusze wyceny
description: "Konfiguracja arkusza wyceny obejmuje dwa cele. Pierwszym celem jest określenie formatu wyświetlania informacji o kosztach sprzedanych towarów, wyprodukowanych towarów oraz zlecenia produkcyjnego. Sformatowane wyświetlenie nosi nazwę arkusz wyceny. Drugim celem jest określenie podstawy obliczania kosztów pośrednich. Konfiguracja arkusza wyceny opiera się na funkcji grupy kosztów dla wyświetlania informacji oraz wzorów obliczania kosztów pośrednich. Oba cele konfigurowania arkusza wyceny są opisane w tym artykule."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostSheetDesigner
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 53201
ms.assetid: e7d72b43-3892-49ae-8821-9eede3f4d24a
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 3988bd478cfad791b5d4c73d28a86c9cfb68288f
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="costing-sheets"></a>Arkusze wyceny

[!include [banner](../includes/banner.md)]

Konfiguracja arkusza wyceny obejmuje dwa cele. Pierwszym celem jest określenie formatu wyświetlania informacji o kosztach sprzedanych towarów, wyprodukowanych towarów oraz zlecenia produkcyjnego. Sformatowane wyświetlenie nosi nazwę arkusz wyceny. Drugim celem jest określenie podstawy obliczania kosztów pośrednich. Konfiguracja arkusza wyceny opiera się na funkcji grupy kosztów dla wyświetlania informacji oraz wzorów obliczania kosztów pośrednich. Oba cele konfigurowania arkusza wyceny są opisane w tym artykule. 

Arkusz wyceny jest sformatowanym widokiem informacji dotyczących kosztu towarów, które są sprzedawane dla produkowanego elementu lub zlecenia produkcyjnego. Podczas konfigurowania arkusza wyceny trzeba zdefiniować format dla informacji, a także zdefiniować podstawę do obliczania kosztów bezpośrednich. Konfiguracja arkusza wyceny opiera się na funkcjach grupy kosztów do wyświetlania informacji oraz dla wzorów używanych do obliczania kosztu pośredniego. Poniżej przedstawiono więcej informacji o dwóch celach konfiguracji arkusza wyceny:
-   **Zdefiniowanie formatu arkusza kosztów.** Format zdefiniowany przez użytkownika dla arkusza kosztów identyfikuje segmentację kosztów, które składają się z kosztu wyprodukowanych elementów sprzedanych towarów. Na przykład informacje o koszcie własnym sprzedaży mogą być posegmentowane według materiałów, robocizny i kosztów ogólnych, na podstawie grup kosztów. Te grupy kosztów są skojarzone z towarami, kategoriami kosztów na potrzeby operacji marszruty oraz formułami obliczania kosztów pośrednich. Format arkusza wyceny z reguły wymaga sum pośrednich, gdy zostało zdefiniowanych wiele grup kosztów. Na przykład można agregować wiele grup kosztów powiązanych z materiałem. Definicja formatu arkusza wyceny jest opcjonalna, ale format arkusza kosztów musi być zdefiniowany, jeśli będą obliczane koszty pośrednie.
-   **Określ podstawę obliczania kosztów pośrednich.** Koszty pośrednie odzwierciedlają ogólnych kosztów produkcji skojarzone z produkcją wyprodukowanego towaru. Formuła obliczania kosztów pośrednich może być określona jako dopłata lub stawka. Dopłata reprezentuje wartość procentową wartości, natomiast stawką stanowi kwotę na godzinę dla operacji marszruty. Grupa kosztów definiuje podstawy wzoru obliczeniowego, np. 100 procent dopłat dla grupy kosztów robocizny lub stawkę godzinową 50,00 USD dla grupy kosztów komputera. Aby zdefiniować wzór obliczeniowy i podstawę jego grupy kosztów, konfiguracja arkusza wyceny wymaga identyfikacji grupy kosztów, która dotyczy kosztów ogólnych i wyboru dopłaty lub stawki.

Każdy wzór obliczeniowy musi zostać wprowadzony jako rekord kosztów. Rekord kosztów składa się z określonej wersji wyceny, wartości procentowej dopłaty (lub wartości kwotowej stawki), podstawy grupy kosztów, stanu oraz daty wprowadzenia. Rekord kosztu początkowo jest wprowadzany ze stanem **Oczekujący** oraz datą wprowadzenia. Aktywacja rekordu kosztu towaru aktualizuje stan (do wartości Aktywny) i datę wprowadzenia (do daty aktywacji). Rekord kosztu może również określać oddział dla wzoru obliczeniowego właściwy dla danego oddziału. Alternatywnie, można pozostawić pole **Oddział** puste, aby wskazać, że wzór obliczeniowy dotyczy całej firmy. Rekord kosztów może opcjonalnie składać się z wyszczególnionego towaru lub grupy towarów, gdy wzór obliczeniowy został zaznaczony jako wzór dla towaru. 

Aktualnie aktywne rekordy kosztów dla formuły obliczania kosztów pośrednich stanowią podstawę oszacowania kosztów zlecenia produkcyjnego. Te zostaną również użyte do obliczania kosztów rzeczywistych, związanych z rzeczywistym zużyciem czasu i materiałów. Oczekujące rekordy kosztów są używane w obliczeniach listy składowej (BOM) dla daty przyszłej. 

Dwie polityki blokowania dla wersji wyceny określają, czy koszty oczekujące mogą być obsługiwane oraz czy koszty oczekujące mogą być rozpoczęte. Użyj polityki blokowania do umożliwienia obsługi danych, a następnie do uniemożliwienia obsługi danych dla danych kosztów w ramach wersji wyceny. 

Po zdefiniowaniu formatu arkusza wyceny oraz obliczeniach dla kosztów pośrednich, należy przeprowadzić oddzielną procedurę zatwierdzania i zapisania informacji. Arkusz wyceny reprezentuje format ogólnofirmowy w celu spójnego przedstawiania informacji dotyczących kosztów sprzedanych towarów. 

Arkusz wyceny jest wyświetlany jako część strony **Obliczanie kosztu pozycji**. Arkusz wyceny może być wyświetlany dla rekordu obliczonego kosztu wytwarzanego towaru na stronie **Cena towaru** lub dla rekordu obliczania właściwego dla zamówienia na stronie **Wyniki obliczeń BOM**. Może być on również wyświetlony jako część strony **Obliczanie ceny** dla zlecenia produkcyjnego.






