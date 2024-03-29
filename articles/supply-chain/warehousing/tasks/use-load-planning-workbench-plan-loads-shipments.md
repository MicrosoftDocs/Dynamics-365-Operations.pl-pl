---
title: Planowanie ładunków i wysyłek za pomocą pulpitu planowania wysyłki ładunku
description: W tym artykule pokazano sposób używania pulpitu planowania wysyłki ładunku w celu utworzenia ładunku dla zamówienia sprzedaży.
author: Mirzaab
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSHistory, WHSLoadTable, WHSLoadPlanningListPage, WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0e53b7667dd4589a7c6c14b8aaf8ba51017eee0d
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9068339"
---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a>Planowanie ładunków i wysyłek za pomocą pulpitu planowania wysyłki ładunku

[!include [banner](../../includes/banner.md)]

W tym artykule pokazano sposób używania pulpitu planowania wysyłki ładunku w celu utworzenia ładunku dla zamówienia sprzedaży. Warunkiem wstępnym jest utworzenie zamówienia sprzedaży, co zrobimy najpierw. Ta procedura jest częścią codziennej pracy koordynatora transportu. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="create-a-sales-order"></a>Utwórz zamówienie sprzedaży
1. Otwórz **Okienko nawigacji > Moduły > Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia zakupu**.
2. Wybierz pozycję **Nowy**.
3. W polu **Konto konta** kliknij rozwijany przycisk, aby otworzyć wyszukiwanie.
4. Wybierz konto **US-004**.
5. Kliknij przycisk **OK**.
6. W polu **Numer produktu** kliknij rozwijany przycisk, aby otworzyć wyszukiwanie.
7. Wybierz towar **A0001**. Towar **A0001** jest włączony dla zarządzania transportem.  
8. W polu **Oddział** wybierz przycisk rozwijany, aby otworzyć wyszukiwanie, a następnie wybierz towar.
9. W polu **Ilość** wpisz liczbę.
10. W polu **Magazyn** wpisz „24” na potrzeby tego przykładu. Ten magazyn jest włączony dla zarządzania transportem i zaawansowanego zarządzania magazynem (WMS).  
11. Wybierz opcję **Zapisz**.
12. Zamknij stronę.

## <a name="create-a-new-load"></a>Tworzenie nowego ładunku
1. Otwórz **Okienko nawigacji > Moduły > Zarządzanie transportem > Planowanie > Warsztat planowania wysyłki ładunku**.
2. Wybierz kartę **Wiersze sprzedaży**. Teraz utworzysz ładunek dla utworzonego właśnie zamówienia sprzedaży. Ładunki można tworzyć na podstawie podaży i popytu z zamówień zakupu, zamówień przeniesienia i zamówień sprzedaży.  
3. W okienku akcji wybierz opcję **Popyt i podaż**.
4. Wybierz opcję **Do nowego ładunku**.
5. W polu **Identyfikator szablonu ładunku** wybierz przycisk rozwijany, aby otworzyć wyszukiwanie. Szablon Ładunek określa maksymalne parametry wagi i objętości całego ładunku. Na przykład szablon ładunku może reprezentować rozmiar kontenera lub ciężarówki. Wybierz towar.
6. Kliknij przycisk **OK**.

## <a name="rate-and-route-the-load"></a>Ustawiania stawek i wyznaczania trasy dla ładunku
1. Wybierz opcję **Ustawianie stawek i wybór trasy**.
2. Wybierz opcję **Pulpit ustalania stawek i wyznaczania tras**.
3. Wybierz opcję **Szukanie najlepszej stawki**.
4. Na liście znajdź i zaznacz odpowiedni rekord.
5. Wybierz opcję **Przypisz**.
6. Zamknij stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]