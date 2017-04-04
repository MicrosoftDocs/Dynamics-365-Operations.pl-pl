---
title: "Tworzenie dokumentacji lub szkolenia przy użyciu nagrań zadań"
description: "W tym temacie wyjaśniono, co Rejestrator zadań i zadań prowadnice, jak utworzyć zadanie nagrań i jak dostosować zadanie w programie Microsoft prowadzi i uwzględnić je w Pomocy."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysHelpSetup
audience: Application User, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 25391
ms.assetid: 59bf39f8-1464-441e-8b23-9a856c73471b
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b21fd97426b331726c12ea29f89817a46dd445c3
ms.openlocfilehash: 38bce4a843f0db575c8d1ba08b7dc2ece8366663
ms.lasthandoff: 03/31/2017


---

# <a name="create-documentation-or-training-using-task-recordings"></a>Tworzenie dokumentacji lub szkolenia przy użyciu nagrań zadań
W tym temacie wyjaśniono, co Rejestrator zadań i zadań prowadnice, jak utworzyć zadanie nagrań i jak dostosować zadanie w programie Microsoft prowadzi i uwzględnić je w Pomocy.

<a name="learn-about-task-recorder"></a>Więcej informacji o Rejestratorze zadań
-------------------------

Program Task recorder jest Microsoft Dynamics 365 dla operacji narzędzie, które służy do rejestrowania czynności wykonanych w interfejsie użytkownika (UI) produktu. Przy użyciu Rejestratora zadań wszystkie zdarzenia wykonywane w interfejsie użytkownika, które są wykonywane na serwerze — takie jak dodawanie wartości, zmiana ustawień i usuwanie danych — są przechwytywane. Zapisywane kroki są zbiorczo zwane *nagraniami zadań*. Nagrania zadań mogą być używane na wiele sposobów:

-   **Nagrania zadań mogą być odtwarzane jako przewodniki po zadaniach.** Zadanie prowadnice są integralną część 365 Dynamics dla obsługi operacji pomocy. Przewodnik zadania jest kontrolowane, z przewodnikiem, interaktywne doświadczenie przez kolejne kroki procesu biznesowego. Użytkownik otrzymuje polecenia wykonania kolejnych kroków w wyskakujących okienkach (lub „dymkach”), które są animowane w interfejsie użytkownika i wskazywać elementy, których użytkownik powinien użyć. "Bąbelkowy" dostarcza również informacji na temat sposobu interakcji z elementu, takie jak "Kliknij tutaj" lub "W tym polu należy wprowadzić wartość". Przewodnik zadań jest uruchamiana przez użytkownika bieżącego zestawu danych i wprowadzane dane są zapisywane w środowisku użytkownika.
-   **Nagrania zadań mogą być wyświetlane jako kroki proceduralne w okienku Pomoc.** Okienko Pomoc do wyszukiwania i wyświetlania zadań nagrań. Okienko Pomocy można uzyskać, klikając **?** Ikona w górnym pasku nawigacyjnym albo można użyć kombinacji klawiszy skrótów, **klawisze Ctrl + Shift +?**. Można odczytać kroki zadania nagrywania w okienku Pomoc, lub można zdecydować, aby odtworzyć nagranie jako przewodnik zadań, więc prowadzi użytkownika przez interfejs użytkownika.
-   **Nagrania zadań można zapisać w BPM.** Nagrania zadań można zapisać w wierszu hierarchii w bibliotece narzędzia do modelowania procesów biznesowych (BPM) w usługach cyklu życia (LCS). Listę czynności i schemat blokowy procesu biznesowego będą generowane z nagrania. Nagrania zadań, które zostały zapisane w bibliotece BPM może być pokazana w 365 Dynamics dla operacji, jak pomóc.
-   **Nagrania zadań mogą być zapisywane jako dokumenty programu Word.** To pozwala łatwo tworzyć przewodniki szkoleniowe nadające się drukowania.

Można utworzyć własnych nagrań zadania, odtwarzanie nagrań zadań dostarczony przez firmę Microsoft lub zmodyfikować nagrania zadań udostępnionych przez firmę Microsoft, aby odzwierciedlać konfiguracji. Aby uzyskać więcej informacji na temat programu Task recorder, zobacz [Rejestrator zadań w usłudze Dynamics 365 dla operacji](task-recorder.md).

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
-   Do każdego kroku w nagraniu zadaniu można utworzyć adnotacje. Podczas odtwarzania przewodnika po zadaniu adnotacje wyświetlają się w „dymku” jako notatki nad lub pod tekstem dla kroku. Gdy wyświetlany jako tekst w okienku Pomoc, adnotacje są wyświetlane jako tekst wbudowany w kroku. Tak samo jak przy opisie dobrze jest zapisać adnotacje w oddzielnym dokumencie. Podczas nagrywania zadania wytnij i wklej adnotacje w z tego dokumentu.

**Różne typy adnotacji** Wszystkie adnotacje są opcjonalne. Należy je dodawać tylko wówczas, gdy zawierają informacje pomocne dla użytkownika.

-   **Tytuł**: adnotacja tytuł pojawi się przed generuje tekst krok, który automatycznie task recorder. W przewodniku zadania adnotacji tytuł pojawia się nad automatycznie wygenerowany tekst. Użyj tego typu adnotacji, aby wyjaśnić, dlaczego użytkownik wykonuje krok lub aby podać dodatkowy kontekst.

To jest okienko edycji, wyświetlane po dodaniu adnotacji podczas tworzenia nagrania. Wprowadź adnotację tytułu w polu **Tytuł**. 

[![ekran1](./media/screen1.png)](./media/screen1.png) 

Tak wygląda adnotacja tytułu w „dymku” w przewodniku po zadaniu. 

[![screen2](./media/screen2.png)](./media/screen2.png)

-   **Uwagi:** adnotacja uwag pojawia się pod tekście kroku generowanym automatycznie przez rejestrator zadania. W przewodniku po zadaniu będzie ona widoczna tylko wówczas, gdy użytkownik kliknij łącze **Pokaż więcej** w dymku przewodnika po zadaniu. Ten typ adnotacji służy do opisywania wszystkich elementów, które należy poznać, aby wykonać krok.

To jest okienko edycji, wyświetlane po dodaniu adnotacji podczas tworzenia nagrania. Wprowadź adnotację uwag w polu **Uwagi**. 

[![screen3](./media/screen3.png)](./media/screen3.png) 

Jest to, jak wygląda adnotacji notatki w "Bąbelkowy" w podręczniku zadania.

[![screen4](./media/screen4.png)](./media/screen4.png)

-   **Informacje o kroku**: adnotacje te są tworzone przez kliknięcie prawym przyciskiem myszy na formancie lub w dowolnym miejscu na formularzu &lt;**programu Task recorder**&lt; ** etap dodawania informacji. ** Informacje o kroki są wyświetlane jako numerowane krok w dowolnym miejscu Wstaw go, mimo że zarejestrowano żadnej akcji w interfejsie użytkownika. Można dodać krok informacji na poziomie formularza lub krok informacji skojarzony z formantem. Jeśli krok informacji jest skojarzony z formularzem, „dymek” przewodnika po zadaniu będzie wyświetlany gdzieś w formularzu, bez wskaźnika, podczas odtwarzania podręcznika po zadaniu. Kiedy to krok info jest skojarzona z żadnym formantem, przewodnik zadanie "Bąbelkowy" wskaż formantu podczas odtwarzania przewodnik zadania. W okienku pomocy adnotacji krok informacje pojawią się jako numerowanego kroku z dowolnie wybrany tekst wprowadzony. Informacje o czynności umożliwia przygotowanie użytkownikowi opisano kroki, które muszą być wykonane poza 365 Dynamics dla operacji lub odnoszą się do innych nagrań (choć nie można utworzyć hyperinks w adnotacjach.) dla następnych kroków.

**Określenia, jak długie ma być nagranie**

-   Użytkownik będzie generalnie czytał lub odtwarzał nagranie od początku do końca, więc nie łączyć kroków lub zadań, które są lepiej wykonywane oddzielnie.
-   Nie należy nagrywać długich scenariuszy, które obejmują wiele procesów podrzędnych. Na przykład „Obsługa stanowiska obsługi klienta w sklepie” jest zbyt rozległym scenariuszem i należy go podzielić na krótsze zadania, np. „Przyjmowanie zwrotów” i „Dodawanie kart upominkowych”.
-   Jeśli zadanie może być wykonane jako część innych procesów biznesowych, należy utworzyć dla nich oddzielne nagrania i odwołać się do nich w innych nagraniach.
-   Jeśli proces obejmuje wiele zadań, które zwykle wykonuje się za jednym razem, można zostawić zadania w jednym nagraniu, np. „Konfigurowanie i przypisywanie profili funkcjonalności”.
-   Jeśli jest to proces, który wykonuje się raz (np. konfiguracja), a zaraz po nim wykonuje się inne zadanie, które można wykonywać wielokrotnie i samodzielnie, należy podzielić je na dwa nagrania.

**Określanie miejsca w interfejsie użytkownika, aby rozpocząć nagrywanie** strony, które znajdują się na po rozpoczęciu nagrywania nagrywania zadań wpływa na którą stronę przewodnika zadania jest wyświetlany dla. Na przykład chcąc nagrywania zadań do wymienionych w okienku pomocy, gdy użytkownik kliknie przycisk Pomoc na stronie Parametry księgi głównej, należy uruchomić nagrywanie na stronie Parametry księgi głównej. **Zapisz nagrania jako pliki .axtr** Po zakończeniu tworzenia lub edytowania nagrania zadania, masz kilka opcji pobrania lub zapisania nagrania. Możesz pobrać plik jako pakiet nagrania zadania (.axtr), nieprzetworzony plik nagrania (.xml), dokument programu Word lub zapisać plik w bibliotece LCS. Dobrze jest zapisać nagranie zadania jako plik pakietu nagrania zadania (.axtr). To ułatwia obsługę plików, jeśli później trzeba zmienić procedury lub adnotacje. Jeśli chcesz pobrać ten plik jako dokument programu Word, zapisz go również jako plik pakietu nagrania zadania.

## <a name="create-your-task-recording"></a>Tworzenie nagrania zadania
Aby uzyskać szczegółowe omówienie czynności, zobacz [jak utworzyć nagranie zadania](task-recorder.md).

## <a name="copy-and-customize-microsofts-task-recordings"></a>Kopiowanie i dostosowywanie nagrań uzyskanych od firmy Microsoft
Można pobrać i edytować nagrania zadania firmy Microsoft na ich użycie dla własnych dokumentacji pomocy lub materiały szkoleniowe. Aby pobrać nagranie zadania od Microsoft, wykonaj następujące czynności:

1.  W usłudze Dynamics 365 dla operacji otwórz program Task recorder. Rejestrator zadań znajduje się w menu **Ustawienia**.
2.  W okienku Rejestratora zadań kliknij przycisk **Obsługa rejestracji.**
3.  W obszarze **Gdzie znajduje się nagranie** kliknij przycisk **Jest w bibliotece LCS**.
4.  Kliknij **Wybierz bibliotekę usługi LCS**.
5.  Wybierz bibliotekę Microsoft global.
6.  W drzewie wybierz węzeł biblioteki procesów biznesowych, z którym jest skojarzone nagranie zadania.
7.  Kliknij przycisk **OK**
8.  Kliknij **Uruchom**.
9.  W tym momencie krok przez rejestrację, zmieniających się wszelkie czynności jak go zarejestrować je ponownie. **Uwaga**: Jeśli trzeba zmienić tekst nagrania, możesz otworzyć nagrywania w **edytowanie adnotacji nagrania** tryb, a następnie zapisz go.
10. Po odtworzeniu nagrania do końca, kliknij **Stop** na pasku rejestratora zadań w górnej części ekranu.
11. Wybierz, jak chcesz zapisać nagranie zadania.

## <a name="include-your-task-recordings-in-the-help-pane"></a>Zawierają nagrania swoje zadania w okienku Pomoc
Aby wyświetlić nagrania niestandardowego zadania w okienku Pomoc, tak, że mogą być odtwarzane jako prowadnice zadań lub wyświetlić w postaci tekstowej, można zapisać nagrania zadania do biblioteki BPM, a następnie zaktualizuj parametry Twojego systemu pomocy do punktu do biblioteki BPM. Aby uzyskać więcej informacji, zobacz [podłączenia systemu pomocy.](../get-started/help-connect.md)

<a name="see-also"></a>Informacje dodatkowe
--------

[Pomoc Dynamics 365 dla operacji](..\get-started\help-overview.md)

[Podłącz pomocy](..\get-started\help-connect.md)

[Program Task Recorder w systemie Dynamics 365 dla operacji](task-recorder.md)

[Ostatnio dodane funkcje Rejestrator zadań](\core\get-started\recently-added-editing-features-in-task-recorder)

[Tworzenie nowej biblioteki szkolenia dla systemu Dynamics AX w ramach cyklu życia usługi za pomocą programu Task recorder (łącze zewnętrzne)](https://docs.com/mufife/163372c6-f366-4c5a-94fa-93e2c25f878a/creating-new-training-libraries-for-dynamics-ax)

[Tworzenie bogatych tematy Pomocy z Rejestrator zadań (łącze zewnętrzne)](https://mbspartner.microsoft.com/AX/Videos/970)


