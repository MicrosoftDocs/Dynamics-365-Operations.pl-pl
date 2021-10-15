---
title: Podwykonawstwo
description: Ten temat pomoże stworzyć przewodnik funkcjonalności podwykonawstwa w produkcji w programie Dynamics 365 Supply Chain Management.
author: johanhoffmann
ms.date: 09/28/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4c4ef554406c727cc410f8dca5f41264be01060b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579359"
---
# <a name="subcontracting"></a>Podwykonawstwo

[!include [banner](../includes/banner.md)]

Ten temat pomoże stworzyć przewodnik funkcjonalności podwykonawstwa w produkcji w Microsoft Dynamics 365 Supply Chain Management. W pierwszej części tego tematu opisano konfigurację danych. Druga część prowadzi przez kolejne kroki przewodnika.

## <a name="target-audience"></a>Odbiorcy docelowi

W tym temacie dowiesz się, jak skonfigurować podwykonawstwo w produkcji. Wykorzystując istniejące dane z firmy HQUS, skonfigurujesz podstawowe ustawienia przepływu działań podwykonawczych. Dane demonstracyjne firmy HQUS obejmują parametry konfiguracyjne, w których wstępnie ustawiono obsługę kroków przewodnika. Co prawda przewodnik nawiązuje do głównych problemów i wyzwań występujących w różnych rolach, ale całość może wykonać administrator systemu.

## <a name="demo-scenario"></a>Scenariusz demonstracji

W firmie HQUS są wytwarzane głośniki wysokiej jakości. W procesie produkcji głośniki przechodzą przez następujące trzy operacje.

- **Wstępny montaż** — jest montowana obudowa głośnika. Materiał na obudowę jest pobierany z magazynu materiałów przed rozpoczęciem operacji.
- **Malowanie** — po zmontowaniu głośnika należy go pomalować. Ta operacja jest wykonywana przez zewnętrznego dostawcę (podwykonawcę). Wstępnie złożona obudowa głośnika jest wysyłana do podwykonawcy świadczącego usługi lakiernicze razem z dwoma materiałami.
- **Wykańczanie** — gdy podwykonawca pomaluje wstępnie złożoną obudowę głośnika, wraca ona do firmy HQUS, która dokonuje końcowego montażu głośnika.

Poniższa ilustracja przedstawia trzy operacje oraz materiały, które są w nich wykorzystywane.

![Operacje Wstępny montaż, Malowanie i Wykańczanie, oraz zużywane w nich materiały.](./media/subcontract01_operations-materials.png)

## <a name="setup"></a>Konfiguracja

Przed rozpoczęciem przewodnika należy skonfigurować dane.

### <a name="set-up-the-finished-product"></a>Konfigurowanie wyrobu gotowego

Ta procedura prowadzi przez konfigurowanie zwolnionego produktu D8100 „Pomalowana obudowa”.

1. Wybierz kolejno opcje **Zarządzanie informacjami o produktach \> Produkty \> Zwolnione produkty**, aby otworzyć stronę **Szczegóły zwolnionego produktu**.
2. W polu szybkiego filtru wpisz **D8100**, aby znaleźć istniejący zwolniony produkt.

    ![Filtrowanie w celu znalezienia zwolnionego produktu D8100 na stronie Szczegóły zwolnionego produktu.](./media/subcontract02_filtering-released-products.png)

3. W okienku akcji na karcie **Konstruuj** wybierz opcję **Marszruta**, aby otworzyć stronę **Marszruta**.

    Strona **Marszruta** zawiera osiem wersji marszruty zwolnionego produktu D8100. Osiem wersji marszruty jest rozdzielonych między cztery marszruty w oddziałach 1 i 5. Marszruta 000400 jest używana do wyceny, marszruta 00041 jest używana w sytuacji, gdy operacja Malowanie jest wykonywana wewnętrznie, a marszruta 00042 jest stosowana dla operacji Malowanie zlecanej na zewnątrz.

    ![Osiem wersji marszruty na stronie Marszruta.](./media/subcontract03_route-page.png)

4. W górnym okienku w siatce **Wersje** wybierz wersję marszruty **00042** dla oddziału **5**.
5. W dolnym okienku na karcie **Przegląd** wybierz w siatce operację **20** (**Cbnt CtSc**).

    ![Wybrana operacja 20 dla wersji marszruty 00042 w oddziale 5.](./media/subcontract04_route-version-operation.png)

6. Kliknij kartę **Ogólne**.

    Zauważ, że pole **Typ marszruty** jest ustawione na **Dostawca**. Ta wartość wskazuje, że operacja 20 (Cbnt CtSc) jest operacją podwykonawczą.

    ![Pole Typ marszruty z ustawioną wartością Dostawca na karcie Ogólne.](./media/subcontract05_general-tab.png)

7. Kliknij kartę **Zapotrzebowanie na zasoby**.

    Do wyszukiwania odpowiednich zasobów podczas planowania produkcji będą wykorzystywane możliwości. Dla operacji 20 (Cbnt CtSc) zauważ, że jest wymagany zasób mający dwie możliwości — **Malowanie** i **Malowane obudowy**.

    ![Możliwości Malowanie i Malowane obudowy na karcie Zapotrzebowanie na zasoby.](./media/subcontract06_resource-requirements-tab.png)

8. Wybierz opcję **Pasujące zasoby**, aby otworzyć okno dialogowe **Pasujące zasoby**.

    Zostały znalezione trzy zasoby spełniające zapotrzebowania na zasoby dla operacji. Zauważ, że zasoby 8851 i 8852 są typu **Dostawca**.

    ![Trzy właściwe zasoby w oknie dialogowym Pasujące zasoby.](./media/subcontract07_applicable-resources-dialog.png)

9. Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Pasujące zasoby** i wrócić do strony **Marszruta**.
10. Zamknij stronę **Marszruta**, aby wrócić do strony **Szczegóły zwolnionego produktu**.

    ![Strona Szczegóły zwolnionego produktu.](./media/subcontract08_released-product-details-page.png)

11. W okienku akcji na karcie **Konstruuj** wybierz opcję **Wersje BOM**, aby otworzyć stronę **Wersje BOM**.

    Na stronie **Wersje BOM** znajdują się cztery wersje listy składowej (BOM) zwolnionego produktu D8100. BOM 000040 służy do wyceny i planowania, BOM 000041 do operacji Malowanie wykonywanej w zakładzie, a BOM 000042 i 000043 do operacji Malowanie wykonywanych przez podwykonawcę.

    Zauważ, że pozycja S8050 jest produktem o typie towaru **Usługa**. Ta pozycja reprezentuje pracę podwykonawczą.

    ![Cztery wersje BOM na stronie Wersje BOM.](./media/subcontract09_bom-versions-page.png)

12. Na skróconej karcie **Wiersze listy składowej (BOM)** wybierz opcję **Edytuj**, aby otworzyć okno dialogowe **Edytuj wiersz BOM**.

    Gdy dla zwolnionego produktu D8100 zostanie utworzone i oszacowane zlecenie produkcyjne, dla towaru S8050 zostanie automatycznie wygenerowane zamówienie zakupu. To zamówienie zakupu będzie połączone ze zleceniem produkcyjnym. Aby zamówienia zakupu były generowane automatycznie, pole **Typ wiersza** musi mieć wartość **Dostawca** oraz musi być wybrane konto dostawcy dla podwykonawcy. W tym przypadku kontem dostawcy jest US-801.

    Zauważ, że wiersz BOM jest połączony z operacją Malowanie za pośrednictwem numeru operacji (w tym przypadku 20).

    ![Okno dialogowe Edytuj wiersz BOM.](./media/subcontract10_edit-bom-line-dialog.png)

### <a name="create-a-password-for-warehouse-workers"></a>Tworzenie hasła dla pracowników magazynu

Należy utworzyć hasło dla pracowników magazynu używających ręcznego urządzenia.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Pracownik**, aby otworzyć stronę **Użytkownicy pracy**.
2. Na skróconej karcie **Użytkownicy** zaznacz wiersz użytkownika **51**.

    ![Strona Użytkownicy pracy.](./media/subcontract11_work-users-page.png)

3. Wybierz opcję **Resetuj hasło**.
4. W polach **Hasło** i **Potwierdź hasło** wprowadź **1**.
5. Wybierz opcję **Ustaw hasło**.

## <a name="step-by-step-walkthrough"></a>Przewodnik krok po kroku

**Scenariusz i kontekst**

Zlecenie produkcyjne na 10 sztuk jest tworzone dla produktu D8100 „Pomalowana obudowa”. Malowanie obudów jest operacją zlecaną na zewnątrz, wykonywaną u dostawcy US-801 Perfect Coating Solutions. Zlecenie produkcyjne obejmuje trzy operacje. W pierwszej operacji obudowa jest wstępnie montowana wewnętrznie w zakładzie. Materiał do wstępnego montażu jest zwalniany do pobrania w magazynie surowców. Po zakończeniu wstępnego montażu wstępnie złożona obudowa jest wysyłana do Perfect Coating Solutions razem z dwoma materiałami, które są wymagane do operacji Malowanie. Po odebraniu pomalowanej obudowy od dostawcy przechodzi ona w zakładzie końcową operację montażu, po czym jest zgłaszana jako wyrób gotowy.

1. Wybierz kolejno opcje **Kontrola produkcji \> Zlecenia produkcyjne \> Wszystkie zlecenia produkcyjne**, aby otworzyć stronę **Wszystkie zlecenia produkcyjne**.
2. W okienku akcji wybierz opcję **Nowe zlecenie produkcyjne**, aby otworzyć okno dialogowe **Tworzenie zlecenia produkcyjnego**.

    ![Okno dialogowe Tworzenie zlecenia produkcyjnego.](./media/subcontract12_create-production-order-dialog.png)

3. W polu **Numer pozycji** wybierz wartość **D8100**.
4. Po wybraniu numeru towaru pojawią się pola wymiarów magazynowych. W polu **Kolor** wybierz wartość **Chrom**.

    Pojawi się okno komunikatu z pytaniem, czy należy wstawić aktywne wersje BOM i marszruty.

    ![Okno komunikatu.](./media/subcontract13_message-box.png)

5. Wybierz opcję **Tak**. 

    W oknie dialogowym **Tworzenie zlecenia produkcyjnego** aktywne wersje BOM i marszruty dla produktu D8100 są automatycznie wybierane odpowiednio w polach **Numer BOM** i **Numer marszruty**. W tym przypadku są zaznaczone wartości BOM **000040** i marszruty **000040**.
    
    > [!NOTE]
    > Zarówno dla BOM, jak i dla marszruty na potrzeby wyceny i planowania jest używana wersja 000040.

6. W polu **Oddział** wybierz wartość **5**.
7. W polu **Magazyn** wybierz wartość **51**.
8. W polach **Numer BOM** i **Numer marszruty** zmień automatycznie wybraną wartość na **000042**.

    > [!NOTE]
    > Zarówno dla BOM, jak i dla marszruty wersja 000042 jest używana do zlecenia podwykonawstwa malowania obudowy do dostawcy US-801.

    ![Wartości ustawiane w oknie dialogowym Tworzenie zlecenia produkcyjnego.](./media/subcontract14_create-production-order-dialog-set.png)

9. Wybierz opcję **Utwórz**, aby utworzyć zlecenie produkcyjne i wrócić do strony **Wszystkie zlecenia produkcyjne**.

    ![Nowe zlecenie produkcyjne na stronie Wszystkie zlecenia produkcyjne.](./media/subcontract15_new-production-order.png)

10. W okienku akcji na karcie **Zlecenie produkcyjne** kliknij opcję **Szacuj**, aby otworzyć okno dialogowe **Szacowanie**.

    ![Okno dialogowe Szacowanie.](./media/subcontract16_estimate-dialog.png)

11. Wybierz opcję **OK**, aby potwierdzić oszacowanie i wrócić do strony **Wszystkie zlecenia produkcyjne**.

    > [!NOTE]
    > Podczas szacowania zlecenia produkcyjnego jest generowane zamówienie zakupu na usługę S8050 dla dostawcy US-801.

12. W okienku akcji na karcie **Zlecenie produkcyjne** wybierz opcję **BOM**, aby otworzyć stronę **BOM**, gdzie można przejrzeć wiersze BOM zlecenia produkcyjnego.

    Dla usługi S8050 zauważ, że istnieje odwołanie do zamówienia zakupu wygenerowanego podczas szacowania zlecenia produkcyjnego.

    ![Wiersze BOM zlecenia produkcyjnego na stronie BOM.](./media/subcontract17_production-order-bom-lines.png)

13. Zamknij stronę **BOM**, aby wrócić do strony **Wszystkie zlecenia produkcyjne**.
14. W okienku akcji na karcie **Harmonogram** kliknij opcję **Planowanie zadań**, aby otworzyć okno dialogowe **Planowanie zadań**.
15. Wprowadź następujące wartości:

    - W polu **Kierunek planowania** wybierz opcję **W przód od jutra**.
    - Ustaw opcję **Ograniczone zdolności produkcyjne** na **Tak**.

    ![Okno dialogowe Planowanie zadań.](./media/subcontract18_job-scheduling-dialog.png)

16. Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Planowanie zadań** i wrócić do strony **Wszystkie zlecenia produkcyjne**.
17. W okienku akcji na karcie **Harmonogram** wybierz opcję **Wykres Gantta**, aby otworzyć stronę **Wykres Gantta — Widok zasobów**.

    Wykres Gantta zawiera graficzną prezentację rozplanowania zasobów w zadaniach produkcyjnych. Zwróć uwagę, że zewnętrzna operacja malowanie składa się z trzech zadań: zadania przetwarzania, zadania transportowania i zadania czasu oczekiwania.

    ![Wykres Gantta na stronie Wykres Gantta — Widok zasobów.](./media/subcontract19_gantt-chart.png)

18. Zamknij stronę **Wykres Gantta — Widok zasobów**, aby wrócić do strony **Wszystkie zlecenia produkcyjne**.
19. W okienku akcji na karcie **Zlecenie produkcyjne** kliknij opcję **Zwolnij**, aby otworzyć okno dialogowe **Zwolnienie**.

    ![Okno dialogowe Zwalnianie.](./media/subcontract20_release-dialog.png)

20. Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Zwalnianie**.
21. Wybierz kolejno opcje **Kontrola produkcji \> Zadania okresowe \> Zwolnij do magazynu \> Automatyczne zwalnianie wierszy BOM i formuły**, aby otworzyć okno dialogowe **Automatyczne zwalnianie wierszy BOM i formuły**.

    ![Okno dialogowe Automatyczne zwalnianie wierszy BOM i formuły.](./media/subcontract21_auto-release-bom-formula-lines-dialog.png)

22. Kliknij przycisk **OK**, aby uruchomić zadanie Automatyczne zwalnianie wierszy BOM i formuły.

    To zadanie zwalnia pracę pobrania surowców do magazynu.

23. Wybierz kolejno opcje **Kontrola produkcji \> Zlecenia produkcyjne \> Wszystkie zlecenia produkcyjne**, aby otworzyć stronę **Wszystkie zlecenia produkcyjne**.
24. Za pomocą pola szybkiego filtru zaznacz zlecenie produkcyjne, nad którym pracujesz.
25. W okienku akcji na karcie **Magazyn** wybierz opcję **Szczegóły pracy**, aby otworzyć stronę **Praca**.

    Zwróć uwagę, że na stronie są widoczne dwa zestawy pracy pobrania surowca. Pierwsza pracy dotyczy materiałów M8100 i M8101. Te materiały są zużywane przez operację 10. Druga pracy dotyczy materiałów M8202 i M8250. Te materiały są zużywane przez operację 20, która jest operacją podwykonawczą.

    ![Dwa zestawy pracy pobrania surowców na stronie Praca.](./media/subcontract22_work-page.png)

26. Uruchom aplikację Warehouse Management, aby wykonać przetwarzanie pracy magazynowej dla operacji 10.

    <!-- TBD – screen shots for processing pick work for the materials. -->

27. Wybierz kolejno opcje **Kontrola produkcji \> Zlecenia produkcyjne \> Wszystkie zlecenia produkcyjne**, aby otworzyć stronę **Wszystkie zlecenia produkcyjne**.
28. Za pomocą pola szybkiego filtru zaznacz zlecenie produkcyjne, nad którym pracujesz.
29. W okienku akcji na karcie **Zlecenie produkcyjne** kliknij opcję **Rozpocznij**, aby otworzyć okno dialogowe **Rozpoczęcie**.
30. Na karcie **Ogólne** wprowadź następujące wartości:

    - W polu **Od nr operacji** wybierz wartość **10**.
    - W polu **Do nr operacji** wybierz wartość **10**.

    ![Wartości ustawiane na karcie Ogólne 1.](./media/subcontract23_start-dialog.png)

31. Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Rozpoczęcie** i wrócić do strony **Wszystkie zlecenia produkcyjne**.

    Zauważ, że stan zlecenia produkcyjnego został zmieniony na **Rozpoczęte**. Materiały dla operacji 10 są używane poprzez automatyczne zaksięgowanie arkusza listy pobrania. Zużycie czasu w operacji 10 jest uwzględniane poprzez automatyczne zaksięgowanie arkusza karty marszruty.

32. Uruchom aplikację Warehouse Management, aby wykonać przetwarzanie pracy magazynowej dla operacji 20.

    <!-- TBD – screen shots for processing pick work for the materials. -->

33. W okienku akcji na karcie **Zlecenie produkcyjne** kliknij opcję **Rozpocznij**, aby otworzyć okno dialogowe **Rozpoczęcie**.
34. Na karcie **Ogólne** wprowadź następujące wartości:

    - W polu **Od nr operacji** wybierz wartość **20**.
    - W polu **Do nr operacji** wybierz wartość **20**.
    - W polu **Ilość** wpisz wartość **10**.
    - W opcji **Księgowanie listy pobrania** wybierz wartość **Nie**.

    ![Wartości ustawiane na karcie Ogólne 2.](./media/subcontract24_general-tab.png)

35. Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Rozpoczęcie** i wrócić do strony **Wszystkie zlecenia produkcyjne**.

    Dla materiałów zużywanych w operacji Malowanie oraz dla usługi zostanie utworzona lista pobrania. Usługa reprezentuje koszt operacji podwykonawczej.

36. W okienku akcji na karcie **Widok** wybierz opcję **Lista pobrania**, aby otworzyć stronę **Lista pobrania**.
37. Zaznacz listę pobrania, która nie jest zaksięgowana, a następnie wybierz numer arkusza, aby wyświetlić wiersze arkusza.

    ![Wiersze arkusza na stronie Lista pobrania.](./media/subcontract25_picking-list.png)

38. W okienku akcji wybierz kolejno opcje **Drukuj** \> **Raport Lista pobrania**, aby otworzyć okno dialogowe **Raport Lista pobrania**.
39. Ustaw opcję **Użyj układu dokumentu dostawy** na **Tak**.

    ![Okno dialogowe Raport listy pobrania.](./media/subcontract26_picking-list-report-dialog.png)

40. Kliknij przycisk **OK**, aby wygenerować raport **Lista pobrania**.

    W tym przypadku jest drukowany dokument dostawy dostawcy z poziomu arkusza listy pobrania do produkcji. Dokument dostawy określa materiały, które zostaną wysłane do dostawcy mającego wykonać operację Malowanie.

    ![Raport list pobrania.](./media/subcontract27_picking-list-report.png)

41. Zamknij raport **Lista pobrania**, aby wrócić do strony **Lista pobrania**.
42. W okienku akcji kliknij opcję **Księguj**, aby otworzyć okno dialogowe **Księgowanie arkusza**.

    ![Okno dialogowe Księgowanie arkusza.](./media/subcontract28_post-journal-dialog.png)

43. Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Księgowanie arkusza**.
44. Otwórz zamówienie zakupu.

    ![Strona Zamówienie zakupu.](./media/subcontract29_purchase-order-page.png)

45. W okienku akcji na karcie **Zakup** wybierz opcję **Potwierdź**.
46. Kliknij przycisk **Księguj**, aby otworzyć okno dialogowe **Księgowanie arkusza**.
47. Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Księgowanie arkusza** i wrócić do strony **Zamówienie zakupu**.
48. Zmień cenę jednostkową z **33** na **40**.

    ![Cena jednostkowa zmieniona na stronie Zamówienie zakupu.](./media/subcontract30_unit-price.png)

49. Ponownie potwierdź zamówienie zakupu.
50. Przyjęcie produktu.

    ![Okno dialogowe Księgowanie dokumentu przyjęcia produktów.](./media/subcontract31_posting-product-receipt-dialog.png)

51. Faktura zakupu.
52. Zaktualizuj stan uzgadniania.

    ![Strona Faktura od dostawcy.](./media/subcontract32_vendor-invoice-page.png)

53. Zgłoś wyroby gotowe.

    ![Okno dialogowe Zgłoszenie wyrobów gotowych.](./media/subcontract33_report-as-finished-dialog.png)

54. Zakończ.

    ![Okno dialogowe Zakończenie.](./media/subcontract34_end-dialog.png)

55. Porównanie kosztów.

    ![Wykresy porównania kosztów.](./media/subcontract35_cost-comparison-charts.png)

Brak danych konfiguracyjnych.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]