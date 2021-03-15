---
title: Opracowywanie struktury wynagrodzeń
description: W tym artykule przedstawiono proces tworzenia stałego planu wynagrodzeń i przypisywania pracowników do planu za pomocą reguł kwalifikowalności.
author: andreabichsel
manager: tfehr
ms.date: 02/10/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: DefaultDashboard, HcmCompensationWorkspace, HcmCompFixedPlansPart, HRMCompFixedPlanTable, HRMCompCreateGridDialog, HRCCompGridView, HRMCompEligibility,  HRCCompGrid
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5a5e7ef2021e41c13b82523f2dc6a1b09bd1ba9f
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115903"
---
# <a name="develop-a-compensation-structure"></a>Opracowywanie struktury wynagrodzeń

W tym artykule przedstawiono proces tworzenia stałego planu wynagrodzeń i przypisywania pracowników do planu za pomocą reguł kwalifikowalności. W tym artykule używane są dane demonstracyjne USMF i dotyczą menedżerów wynagrodzeń i świadczeń.

## <a name="create-a-fixed-compensation-plan"></a>Tworzenie systemu stałych wynagrodzeń

1. Wybierz **Zarządzanie wynagrodzeniami**.

2. Wybierz **Systemy stałych wynagrodzeń**.

3. Wybierz pozycję **Nowy**.

4. Wprowadź wartość w polu **Plan**.

5. W polu **Opis** wprowadź lub wybierz wartość.

6. W polu **Data wejścia w życie** wprowadź datę.

7. W polu **Typ** określ, czy system stałych wynagrodzeń to plan typu **Pasmo**, **Kategoria** lub **Krok**.

8. Pole wyboru **Rekomendacje dozwolone** służy jako wartość domyślna dla wszystkich czynności dodawanych do tego planu w zdarzeniu procesowym. Zezwolenie na rekomendacje umożliwi zastąpienie obliczonej kwoty podstawowej podczas przetwarzania wynagrodzeń.

9. Pole **Tolerancja wyjścia poza zakres** pozwala określić sposób postępowania z kwotami wynagrodzeń, które nie mieszczą się w zakresie podanej struktury wynagrodzeń dla danego poziomu. Ustawienie pola **Tolerancja wyjścia poza zakres** na wartość **Brak** pozwala na użycie dowolnej kwoty wynagrodzenia. **Miękka tolarancja** ostrzega użytkowników, jeśli kwota wynagrodzenia jest mniejsza niż minimalna lub większa niż maksymalna kwota punktu odniesienia dla tego poziomu. Użytkownicy mogą zignorować ostrzeżenie i kontynuować. **Twarda tolerancja** spowoduje generowanie błędu, jeśli wynagrodzenie pracownika zostanie ustawione poza punktami odniesienia minimalnym i maksymalnym dla poziomu, oraz automatycznie dopasowanie wynagrodzenia pracownika, aby się mieściło w tym zakresie.

10. Pole **Reguły zatrudnienia** oblicza wynagrodzenie pracownika podczas zdarzenia procesowego. **Reguła zatrudnienia** **Procentu** oblicza wzrost proporcjonalny do długości czasu zatrudnienia pracownika w cyklu.

11. W polu **Waluta** wpisz wartość.

12. W polu **Konwersja stawki płacy** wprowadź lub wybierz wartość.

13. Rozwiń sekcję **Macierz zakresów wykorzystania**. Opcjonalnie dodaj rekordy zakresu wykorzystania, aby umożliwić pracownikom szybsze dotarcie ich punktów środkowych, a spowolnić osiągnięcie wartości maksymalnej w zakresie.

14. Wybierz opcję **Zapisz**. Spowoduje to włączenie przycisku **Ustaw wynagrodzenie** i kontynuowanie definiowania struktury wynagrodzeń dla planu.

15. Wybierz **Konfiguruj wynagrodzenie**. Możesz utworzyć strukturę wynagrodzeń, korzystając z jednej z trzech poniższych metod:

    - Utworzenie całkowicie nowej struktury przez wybranie zbioru punktów odniesienia i dodanie poziomów, aby utworzyć własną strukturę.
    - Skopiowanie struktury wynagrodzeń z istniejącego planu i jej zmodyfikowanie dla nowego planu.
    - Wybór istniejącej siatki wynagrodzeń. Jeśli inny plan już korzysta z siatki wynagrodzeń, drugi plan również odzwierciedla wszelkie zmiany wprowadzone w siatce.

16. Wybierz **Utwórz nową na podstawie istniejącej macierzy wynagrodzeń**.

17. W polu **Kopiuj z siatki** wprowadź lub wybierz wartość. Opcjonalnie można zmienić nazwę nowej siatki wynagrodzeń, którą tworzysz przez kopiowanie wybranej siatki.

18. Kliknij przycisk **OK**.

19. Wybierz **Zmianę grupową**. **Zmiana grupowa** pozwala zachować kwoty macierzy wynagrodzeń poprzez zastosowanie wzrostu procentowego lub o stałej kwocie do jednego lub więcej poziomów lub punktów odniesienia.

20. W polu **Kwota korekty** wpisz liczbę.

21. Na liście oznacz wszystkie wiersze lub usuń ich oznaczenie.

22. Kliknij przycisk **Zastosuj do siatki**.

23. Zamknij stronę. Po utworzeniu struktury wynagrodzeń możesz wybrać, które punkty odniesienia mają być używane jako punkt kontrolny dla stałego planu wynagrodzeń. Punkt kontrolny służy do obliczania wskaźnika porównawczego pracownika.

24. W polu **Punkt kontrolny** wprowadź lub wybierz wartość.

25. Zamknij stronę.

## <a name="create-an-eligibility-rule-for-the-fixed-compensation-plan"></a>Tworzenie reguły uprawnienia dla systemu stałych wynagrodzeń

Nie możesz przypisać systemu stałych wynagrodzeń pracownikowi, dopóki nie zdefiniujesz reguł kwalifikujących do tego planu.  

1. Wybierz **Reguły uprawnienia**.

2. Wybierz pozycję **Nowy**.

3. Wprowadź wartość w polu **Uprawnienie**.

4. W polu **Opis** wprowadź lub wybierz wartość.

5. W polu **Data wejścia w życie** wprowadź datę. Zarówno stałe, jak i zmienne plany wynagrodzeń wykorzystują zasady kwalifikowalności. W polu **Typ** wybierz typ planu.

6. W polu **Plan** wprowadź lub wybierz wartość. Wybierz kryteria, które pracownik musi spełnić, aby kwalifikować się do planu wynagrodzeń. Kryteria mogą obejmować:

    - **Dział**
    - **Związek zawodowy**
    - **Lokalizację** (**Region wynagrodzenia**)
    - **Zadanie**
    - **Funkcja**
    - **Typ zadania**
    - **Poziom wynagrodzeń**
    
    Aby kwalifikować się do planu wynagrodzeń, pracownik musi spełniać wszystkie kryteria. W razie nieokreślenia żadnych kryteriów wszyscy pracownicy kwalifikują się do planu wynagrodzeń. Jeśli pracownik nie spełnia kryteriów określonych w regule uprawnienia lub jeśli nie określono reguły uprawnienia dla planu wynagrodzeń, plan wynagrodzeń nie pojawi się w wynikach wyszukiwania podczas tworzenia rekordu stałego wynagrodzenia dla pracownika.

7. Zamknij stronę.

8. Zamknij stronę.



[!INCLUDE[footer-include](../includes/footer-banner.md)]