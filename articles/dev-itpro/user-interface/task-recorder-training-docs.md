---
title: "Tworzenie dokumentacji lub szkolenia przy użyciu nagrań zadań"
description: "W tym temacie wyjaśniono, czym jest Rejestrator zadań i przewodniki po zadaniach, jak tworzyć nagrania zadań oraz jak dostosowywać przewodniki po zadaniach firmy Microsoft i umieszczać je w Pomocy."
author: josaw1
manager: AnnBe
ms.date: 10/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: SysHelpSetup
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 25391
ms.assetid: 59bf39f8-1464-441e-8b23-9a856c73471b
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: fbf7edbd141f5e94c333b64beedf9126d2900d47
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="create-documentation-or-training-using-task-recordings"></a>Tworzenie dokumentacji lub szkolenia przy użyciu nagrań zadań

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, czym jest Rejestrator zadań i przewodniki po zadaniach, jak tworzyć nagrania zadań oraz jak dostosowywać przewodniki po zadaniach firmy Microsoft i umieszczać je w Pomocy.

> [!IMPORTANT]
> Można zarejestrować własne przewodniki zadania dla programu Dynamics 365 for Talent, ale nie będzie można zapisać ich w bibliotece Narzędzia do modelowania procesów biznesowych (BPM) ani otworzyć ich w okienku Pomoc. Można zapisać je lokalnie lub w lokalizacji sieciowej, a następnie odtworzyć za pomocą Rejestratora zadań. 

<a name="learn-about-task-recorder"></a>Więcej informacji o Rejestratorze zadań
-------------------------

Rejestrator zadań to narzędzie systemu umożliwiające nagrywanie czynności wykonywanych w interfejsie użytkownika (UI) produktu. Przy użyciu Rejestratora zadań wszystkie zdarzenia wykonywane w interfejsie użytkownika, które są wykonywane na serwerze — takie jak dodawanie wartości, zmiana ustawień i usuwanie danych — są przechwytywane. Zapisywane kroki są zbiorczo zwane *nagraniami zadań*. Nagrania zadań mogą być używane na wiele sposobów:

-   **Nagrania zadań mogą być odtwarzane jako przewodniki po zadaniach.** Przewodniki po zadaniach są integralną częścią systemu Pomocy. Przewodniki po zadaniach oferują interaktywne prezentacje poszczególnych kroków w procesach biznesowych. Użytkownik otrzymuje polecenia wykonania kolejnych kroków w wyskakujących okienkach (lub „dymkach”), które są animowane w interfejsie użytkownika i wskazywać elementy, których użytkownik powinien użyć. „Dymek” zawiera informacje o sposobach obsługi elementu, na przykład „Kliknij tutaj” lub „W tym polu należy wprowadzić wartość”. Przewodnik po zadaniu działa w odniesieniu do bieżącego zestawu danych użytkownika, które są wprowadzane i zapisywane w środowisku użytkownika.
-   **Nagrania zadań mogą być wyświetlane jako kroki procedury w okienku Pomocy.** Okienko Pomocy może być używane do wyszukiwania i wyświetlania nagrań zadań. Okienko Pomocy można wyświetlić, klikając ikonę **?** na górnym pasku nawigacyjnym, albo można użyć skrótu **Ctrl+Shift+?**. Można czytać kroki nagrania zadania w okienku Pomocy lub można wybrać opcję odtwarzania nagrań jako przewodnika po zadaniu, który przeprowadzi Cię przez interfejs użytkownika.
-   **Nagrania zadań można zapisać w BPM.** Nagrania zadań można zapisać w wierszu hierarchii w bibliotece narzędzia BPM w Lifecycle Services (LCS). Listę czynności i schemat blokowy procesu biznesowego będą generowane z nagrania. Nagrania zadań, które zostały zapisane w bibliotece BPM, mogą być wyświetlane jako Pomoc.
-   **Nagrania zadań mogą być zapisywane jako dokumenty programu Word.** To pozwala łatwo tworzyć przewodniki szkoleniowe nadające się drukowania.

Można tworzyć własne nagrania zadań, odtwarzać nagrania zadań udostępnione przez firmę Microsoft lub modyfikować te nagrania zgodnie z własną konfiguracją. Aby uzyskać więcej informacji na temat Rejestratora zadań, zobacz [Rejestrator zadań](task-recorder.md).

## <a name="plan-your-task-recording"></a>Planowanie nagrań zadań
Niezależnie od tego, czy tworzysz najnowsze nagranie, czy opierasz się na nagraniach od Microsoft, pamiętaj o następujących informacjach.

-   Zaplanuj nagranie jak film wideo. Wszystkie decyzje podejmij z wyprzedzeniem.
-   Przeprowadź proces biznesowy raz lub dwa razy przed nagraniem, aby dobrze poznać poszczególne kroki.
-   Podczas wykonywania procesu przed nagraniem zwróć uwagę na miejsca, w których używasz skrótów klawiszowych lub klawisza **Enter**, tak aby nie robić tego podczas nagrania.
-   Odpowiedz sobie na następujące pytania:
    -   Czy chcesz grupować kroki według podzadań? Podzadania odseparowują sekcje procesu wizualnie. Na przykład, jeśli nagrywasz proces „Tworzenie i zwalnianie produktu” możesz grupować kroki, które są wymagane do tworzenia produktu i następnie pogrupować kroki, które są wymagane do wydania produktu. Podzadania poprawiają również czytelność dłuższych procesów.
    -   Czy chcesz dodać adnotacje, a jeśli tak, to gdzie? Zobacz temat „Interpretacja różnych typów adnotacji” poniżej, aby uzyskać więcej informacji.
    -   Jakie wartości dodasz do różnych pól podczas wykonywania kroków procesu biznesowego? Dobrze jest wiedzieć, co wybierzesz lub wpiszesz podczas realizacji procesu, aby nie musieć się cofać i poprawiać pomyłek podczas nagrywania.

**Zapisz opis i adnotacje wcześniej**

-   Na początku każdego nagrania zadania, jest pole opisu, które pozwala na umieszczenie wprowadzenia do nagrania. Dobrze jest zapisać opis wcześniej w oddzielnym dokumencie, by móc skopiować go i wkleić do nagrania podczas nagrywania. Dzięki temu można dobrze zredagować tekst, zanim rozpocznie się nagranie. Dzięki zastosowaniu metody wycinania i wklejania proces nagrywania przebiega szybko i bez przeszkód.
-   Do każdego kroku w nagraniu zadaniu można utworzyć adnotacje. Podczas odtwarzania przewodnika po zadaniu adnotacje wyświetlają się w „dymku” jako notatki nad lub pod tekstem dla kroku. Tekst adnotacji wyświetlany w okienku Pomocy jest wbudowany w dany krok. Tak samo jak przy opisie dobrze jest zapisać adnotacje w oddzielnym dokumencie. Podczas nagrywania zadania wytnij i wklej adnotacje w z tego dokumentu.

**Różne typy adnotacji** Wszystkie adnotacje są opcjonalne. Należy je dodawać tylko wówczas, gdy zawierają informacje pomocne dla użytkownika.

-   **Tytuł:** Adnotacja tytułu pojawia się przed tekstem kroku generowanym automatycznie przez rejestrator zadań. W przewodniku po zadaniu adnotacja tytułu pojawia się nad automatycznie wygenerowanym tekstem. Użyj tego typu adnotacji, aby wyjaśnić, dlaczego użytkownik wykonuje krok lub aby podać dodatkowy kontekst.

To jest okienko edycji, wyświetlane po dodaniu adnotacji podczas tworzenia nagrania. Wprowadź adnotację tytułu w polu **Tytuł**. 

[![screen1](./media/screen1.png)](./media/screen1.png) 

Tak wygląda adnotacja tytułu w „dymku” w przewodniku po zadaniu. 

[![screen2](./media/screen2.png)](./media/screen2.png)

-   **Uwagi:** adnotacja uwag pojawia się pod tekście kroku generowanym automatycznie przez rejestrator zadania. W przewodniku po zadaniu będzie ona widoczna tylko wówczas, gdy użytkownik kliknij łącze **Pokaż więcej** w dymku przewodnika po zadaniu. Ten typ adnotacji służy do opisywania wszystkich elementów, które należy poznać, aby wykonać krok.

To jest okienko edycji, wyświetlane po dodaniu adnotacji podczas tworzenia nagrania. Wprowadź adnotację uwag w polu **Uwagi**. 

[![screen3](./media/screen3.png)](./media/screen3.png) 

Tak wygląda adnotacja uwag w „dymku” w przewodniku po zadaniu.

[![screen4](./media/screen4.png)](./media/screen4.png)

-   **Krok informacji**: Te adnotacje są tworzone za pomocą kliknięcia prawym przyciskiem myszy na formancie lub w dowolnym miejscu w formularzu &lt; **Rejestrator zadań** &lt; **Dodaj krok informacji. **Kroki informacji są wyświetlane jako ponumerowane kroki w punkcie, w którym zostały wstawione, nawet jeśli żadna akcja nie została zarejestrowana w interfejsie użytkownika. Można dodać krok informacji na poziomie formularza lub krok informacji skojarzony z formantem. Jeśli krok informacji jest skojarzony z formularzem, „dymek” przewodnika po zadaniu będzie wyświetlany gdzieś w formularzu, bez wskaźnika, podczas odtwarzania podręcznika po zadaniu. Kiedy krok informacji jest skojarzony z formantem, „dymek” podręcznika po zadaniu będzie wskazywał formant podczas podręcznika po zadaniu. W okienku Pomocy adnotacja informacji o kroku będzie wyświetlana jako ponumerowany krok z dowolnym wprowadzonym tekstem. Instrukcje etapowe pozwalają przygotować użytkownika do kolejnych kroków, opisują kroki, które muszą być wykonane poza programem Microsoft Dynamics 365 for Finance and Operations lub odwołują się do innych nagrań (jednak nie można utworzyć hiperłącza w adnotacji).

**Określenia, jak długie ma być nagranie**

-   Użytkownik będzie generalnie czytał lub odtwarzał nagranie od początku do końca, więc nie łączyć kroków lub zadań, które są lepiej wykonywane oddzielnie.
-   Nie należy nagrywać długich scenariuszy, które obejmują wiele procesów podrzędnych. Na przykład „Obsługa stanowiska obsługi klienta w sklepie” jest zbyt rozległym scenariuszem i należy go podzielić na krótsze zadania, np. „Przyjmowanie zwrotów” i „Dodawanie kart upominkowych”.
-   Jeśli zadanie może być wykonane jako część innych procesów biznesowych, należy utworzyć dla nich oddzielne nagrania i odwołać się do nich w innych nagraniach.
-   Jeśli proces obejmuje wiele zadań, które zwykle wykonuje się za jednym razem, można zostawić zadania w jednym nagraniu, np. „Konfigurowanie i przypisywanie profili funkcjonalności”.
-   Jeśli jest to proces, który wykonuje się raz (np. konfiguracja), a zaraz po nim wykonuje się inne zadanie, które można wykonywać wielokrotnie i samodzielnie, należy podzielić je na dwa nagrania.

**Określ gdzie w interfejsie użytkownika zacząć nagrywanie** Strona, na której jesteś na początku nagrania, ma wpływ na to, dla której strony wyświetlany jest przewodnik po zadaniu. Na przykład jeśli nagranie zadania ma się znaleźć na liście w okienku Pomocy, gdy użytkownik kliknie przycisk Pomocy na stronie parametrów księgi głównej, musisz zacząć nagranie na stronie parametrów księgi głównej. **Zapisz nagrania jako pliki .axtr** Po zakończeniu tworzenia lub edytowania nagrania zadania, masz kilka opcji pobrania lub zapisania nagrania. Możesz pobrać plik jako pakiet nagrania zadania (.axtr), nieprzetworzony plik nagrania (.xml), dokument programu Word lub zapisać plik w bibliotece LCS. Dobrze jest zapisać nagranie zadania jako plik pakietu nagrania zadania (.axtr). To ułatwia obsługę plików, jeśli później trzeba zmienić procedury lub adnotacje. Jeśli chcesz pobrać ten plik jako dokument programu Word, zapisz go również jako plik pakietu nagrania zadania.

## <a name="create-your-task-recording"></a>Tworzenie nagrania zadania
Szczegółowe omówienie znajduje się w temacie [Jak utworzyć nagrania zadań](task-recorder.md).

## <a name="copy-and-customize-microsofts-task-recordings"></a>Kopiowanie i dostosowywanie nagrań uzyskanych od firmy Microsoft
Można pobrać i edytować nagrania firmy Microsoft i używać ich do tworzenia własnej dokumentacji Pomocy lub materiałów szkoleniowych. Aby pobrać nagranie zadania od Microsoft, wykonaj następujące czynności:

1.  Otwórz Rejestratora zadań. Rejestrator zadań znajduje się w menu **Ustawienia**.
2.  W okienku Rejestratora zadań kliknij przycisk **Obsługa rejestracji.**
3.  W obszarze **Gdzie znajduje się nagranie** kliknij przycisk **Jest w bibliotece LCS**.
4.  Kliknij **Wybierz bibliotekę usługi LCS**.
5.  Wybierz globalną bibliotekę Microsoft.
6.  W drzewie wybierz węzeł biblioteki procesów biznesowych, z którym jest skojarzone nagranie zadania.
7.  Kliknij przycisk **OK**
8.  Kliknij **Uruchom**.
9.  Obejrzyj nagranie, zmieniając poszczególne kroki, aby nagrać je ponownie. **Uwaga**: Jeśli wystarczy tylko zmienić tekst nagrania, można otworzyć je w trybie **edytowania adnotacji nagrania**, a następnie zapisać.
10. Po odtworzeniu nagrania do końca, kliknij **Stop** na pasku rejestratora zadań w górnej części ekranu.
11. Wybierz, jak chcesz zapisać nagranie zadania.

## <a name="include-your-task-recordings-in-the-help-pane"></a>Umieszczanie nagrań zadań w okienku Pomocy
Aby wyświetlić własne niestandardowe nagrania zadań w okienku Pomocy, by mogły być odtwarzane jako przewodniki po zadaniach lub wyświetlane jako tekst, należy zapisać nagrania zadań w bibliotece BPM, a następnie zaktualizować parametry systemu Pomocy, aby wskazywał bibliotekę BPM. Aby uzyskać więcej informacji, zobacz [Łączenie z systemem Pomocy](../../fin-and-ops/get-started/help-connect.md).

<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Omówienie Pomocy](../../fin-and-ops/get-started/help-overview.md)

[Nawiązywanie połączenia z Pomocą](../../fin-and-ops/get-started/help-connect.md)

[Rejestrator zadań](task-recorder.md)

[Tworzenie multimedialnych tematów Pomocy z Rejestratorem zadań (łącze zewnętrzne)](https://mbspartner.microsoft.com/AX/Videos/970)

