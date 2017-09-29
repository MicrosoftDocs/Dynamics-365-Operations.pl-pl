--- 
title: "Badanie lub rozwiązywanie wyjątków"
description: "Zasady dotyczące faktur od dostawców są uruchamiane podczas księgowania faktur od dostawców przy użyciu strony Faktura od dostawcy oraz po otwarciu strony naruszeń zasad faktur od dostawców."
author: abruer
manager: AnnBe
ms.date: 02/16/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: f1c279546dfaa738022369f782df57f02afa883e
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="research-or-resolve-exceptions"></a>Badanie lub rozwiązywanie wyjątków

[!include[task guide banner](../../includes/task-guide-banner.md)]

Zasady dotyczące faktur od dostawców są uruchamiane podczas księgowania faktur od dostawców przy użyciu strony Faktura od dostawcy oraz po otwarciu strony naruszeń zasad faktur od dostawców. Można także skonfigurować przepływ pracy faktur od dostawcy, aby uruchamiał zasady dotyczące faktur od dostawców podczas każdego przesłania faktur do przepływu. 

Zasady faktur od dostawców nie dotyczą faktur, które zostały utworzone w rejestrze faktur lub arkuszu faktur. 

Funkcja sprawdzania poprawności uzgadniania faktur nie używa zasad dotyczących faktur od dostawców, ale jest konfigurowana na stronie Parametry modułu rozrachunków z dostawcami.

To nagranie wykorzystuje firmę demonstracyjną USMF. Czynności te wykonuje menedżer ds. rozrachunków z dostawcami lub menedżer księgowości. Zanim rozpoczniesz, upewnij się, że wybrano klucz konfiguracji Uzgadnianie faktur.


## <a name="prepare-to-create-vendor-invoice-policies"></a>Przygotowanie do tworzenia zasad dotyczących faktur od dostawców
1. Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia > Parametry modułu rozrachunków z dostawcami.
2. Kliknij kartę Weryfikacja faktury.
3. Zaznacz lub wyczyść pole wyboru Automatycznie aktualizuj stan nagłówka faktury.
4. Kliknij przycisk OK.
5. W polu Księguj fakturę z rozbieżnościami zaznacz opcję.
6. Zamknij stronę.
7. Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia zasad > Zasady dotyczące faktur od dostawców.
8. Kliknij opcję Parametry.
9. Kliknij przycisk Dodaj.
10. Zamknij stronę.

## <a name="create-policy-rule-types-for-vendor-invoices"></a>Tworzenie typów reguł dla faktur od dostawców
1. Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia zasad > Typy reguł faktur od dostawców.
2. Kliknij przycisk Nowy.
3. W polu Nazwa reguły wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Nazwa kwerendy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście znajdź i zaznacz odpowiedni rekord.
7. Na liście kliknij łącze w wybranym wierszu.
8. Kliknij przycisk Zapisz.
9. Zamknij stronę.

## <a name="define-a-vendor-invoice-policy"></a>Definiowanie zasad dotyczących faktur od dostawców
1. Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia zasad > Zasady dotyczące faktur od dostawców.
2. Kliknij przycisk Nowy.
3. W polu Nazwa wpisz wartość.
4. Wypełnij pole Opis.
5. Rozwiń lub zwiń sekcję Organizacje zasad.
6. W drzewie zaznacz pozycję „Contoso Entertainment System USA”.
7. Kliknij przycisk Dodaj.
8. Rozwiń lub zwiń sekcję Reguły zasad.
9. Kliknij przycisk Utwórz regułę.
10. W polu Opis reguły wpisz wartość.
11. Kliknij przycisk Filtr.
12. Kliknij przycisk Dodaj.
13. Na liście oznacz wybrany wiersz.
14. W polu Tabela kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
15. Na liście kliknij łącze w wybranym wierszu.
16. W polu Tabela pochodna kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
17. Na liście kliknij łącze w wybranym wierszu.
18. W polu Pole kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
19. W polu Pole wpisz wartość.
20. Zamknij stronę.
21. W polu Kryteria wpisz wartość.
22. Kliknij przycisk OK.
23. Kliknij przycisk OK.
24. Zamknij stronę.
25. Zamknij stronę.

