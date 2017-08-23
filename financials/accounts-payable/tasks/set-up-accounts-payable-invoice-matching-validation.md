--- 
title: "Konfigurowanie sprawdzania uzgadniania faktur rozrachunków z dostawcami"
description: "To nagranie wykorzystuje firmę demonstracyjną USMF."
author: abruer
manager: AnnBe
ms.date: 11/14/2016
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 8959cf3a45f42e0ef5f0d79726c63184c274efff
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-accounts-payable-invoice-matching-validation"></a>Konfigurowanie sprawdzania uzgadniania faktur rozrachunków z dostawcami

[!include[task guide banner](../../includes/task-guide-banner.md)]

To nagranie wykorzystuje firmę demonstracyjną USMF. Czynności te wykonuje menedżer ds. rozrachunków z dostawcami lub menedżer księgowości. Zanim rozpoczniesz, upewnij się, że wybrano klucz konfiguracji Uzgadnianie faktur. Jeśli firma śledzi wydatki, na przykład koszty frachtu, przy użyciu opłat, upewnij się, że wybrany został klucz konfiguracji Opłaty.  Uzgadnianie faktur rozrachunków z dostawcami jest procesem uzgadniania obejmującym informacje z faktury dostawcy, zamówienia zakupu i przyjęć produktów. Różnice między tymi dokumentami są nazywane rozbieżnościami (w uzgadnianiu/wykrytymi podczas uzgadniania). Rozbieżności w uzgadnianiu są porównywane z ustawionymi wartościami tolerancji. Jeśli rozbieżność przekracza wartość procentową lub kwotową, są wyświetlane ikony uzgadniania odchyleń w formularzach Faktura od dostawcy i Szczegóły uzgadniania faktur.

1. Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia > Parametry modułu rozrachunków z dostawcami.
2. Kliknij kartę Weryfikacja faktury.
3. Zaznacz lub wyczyść pole wyboru Włącz weryfikację uzgadniania faktur.
    * Wybierz, czy do zaksięgowania uzgadnianej faktury zawierającej rozbieżności wymagane jest jej wcześniejsze zatwierdzenie. Jeśli zaznaczysz opcję Zezwól z ostrzeżeniem, wizualne wskazanie pojawi się, gdy rozbieżność dla uzgadniania faktur przekroczy tolerancję. Jednak będzie można zaksięgować fakturę. Aby korzystać z przepływów pracy razem ze sprawdzaniem poprawności uzgadniania faktur, upewnij się, że pole Księguj fakturę z rozbieżnościami ma ustawioną wartość Zezwól z ostrzeżeniem, aby uniknąć konieczności wielokrotnego zatwierdzania.  
    * W polu Automatycznie aktualizuj stan uzgodnienia nagłówka faktury określ, czy uzgodnienie będzie wykonywane automatycznie podczas wprowadzania danych faktur przez system. Zalecanym ustawieniem jest wartość Tak, chyba że występują problemy z wydajnością podczas wprowadzania danych. Wyłączenie funkcji aktualizacji automatycznych może poprawić wydajność systemu, ponieważ podczas wprowadzania danych będzie pomijane sprawdzanie poprawności uzgadniania faktur,. Jeśli zostanie zaznaczona opcja Nie, pracownik zajmujący się wprowadzaniem danych musi ręcznie zaktualizować stan uzgadniania faktury, aby widzieć wyniki weryfikacji uzgadniania faktury.  
4. Przełącz rozwinięcie sekcji Uzgadnianie sum faktur.
5. Zaznacz lub wyczyść pole Dopasuj sumy faktur, aby uzgadniać rzeczywiste sumy faktur z oczekiwanymi sumami częściowymi.
    * Określ, czy ikona jest wyświetlana, gdy rozbieżność dla uzgadniania faktur przekracza limity tolerancji. Można ustawić wyświetlanie ikony, gdy dodatnia rozbieżność przekracza limity tolerancji lub gdy dodatnia lub ujemna rozbieżność przekracza limity tolerancji.  
    * Przykładowo, tolerancja wynosi 5 procent, a łączna kwota faktury dla zamówienia zakupu to 100. W takim wypadku ikona uzgadniania cen zostanie wyświetlona, jeśli łączna kwota faktury na fakturze przekroczy 105,00. Wybranie opcji Jeśli większe lub mniejsze niż dopuszczalna rozbieżność sprawi, że odpowiednia ikona zostanie również wyświetlona w przypadku kwoty faktury mniejszej niż 95,00.  
6. W polu Dozwolona wartość procentowa rozbieżności sum faktury wpisz liczbę.
7. Przełącz rozwinięcie sekcji Uzgadnianie cen i ilości.
    * W polu Zasady uzgadniania wierszy wybierz wartość, która będzie używana jako domyślna zasada dla firmy, z którą pracujesz. Opcja „Niewymagane” oznacza, że nie będzie wymagana żadna weryfikacja zgodności cen poszczególnych wierszy faktury z cenami w zamówieniu zakupu ani ilości na fakturze z ilościami w dokumencie dostawy. Opcja „Uzgadnianie dwuelementowe” oznacza, że jest wymagana weryfikacja wierszy faktury, ale obejmuje tylko dokumenty zamówień zakupu i faktur od dostawcy. Dokument przyjęcia produktów nie jest brany pod uwagę przy sprawdzaniu poprawności uzgadniania. „Uzgadnianie trzyelementowe” oznacza, że cena jednostkowa netto na fakturze zostanie porównana ceną jednostkową netto w zamówienia zakupu, a ilość na dokumencie przyjęcia produktów zostanie porównana z ilością na fakturze.  
    * Jeśli używasz zasady dwuelementowego lub trzyelementowego uzgadniania wierszy, na stronie rozbieżności cenowych towarów można skonfigurować wartości procentowe rozbieżności cen dla firmy, towarów i dostawców. Gdy faktury dostawców są porównywane z informacjami w zamówieniach zakupu, odpowiednia dozwolona wartość procentowa rozbieżności cen jest wyszukiwana.  
8. W polu Zasady uzgadniania wierszy wybierz opcję.
    * Aby zezwolić na stosowanie różnych poziomów uzgadniania do towaru, dostawcy, kombinacji dostawców i towarów lub wierszy zamówienia zakupu, należy wybrać wartość w polu Zezwalaj na zastępowanie zasad uzgadniania. Zasadę uzgadniania wierszy obowiązującą w firmie można zastąpić dla określonego dostawcy, towaru lub kombinacji dostawcy i towaru na stronie Zasady uzgadniania.  
    * Aby uzgadniać całkowite ceny dla towarów w wierszach na fakturach, należy wybrać wartość w polu Dopasuj ceny całkowite. Ten typ uzgadniania przydaje się, gdy dostawca wysyła wielu faktur dla tego samego wiersza zamówienia zakupu. Istnieje możliwość porównania informacji o cenie netto każdego wiersza na fakturze oraz wszystkich oczekujących i wcześniej zaksięgowanych wierszy faktury z kwotą netto w odpowiednim wierszu zamówienia zakupu.  
9. W polu Dopasuj ceny całkowite wybierz opcję.
10. W polu Tolerancja całkowitej ceny zakupu wpisz liczbę.
11. Przełącz rozwinięcie sekcji Uzgadnianie opłat.
12. Aby uzgadniać rzeczywiste opłaty z opłatami oczekiwanymi zgodnie z informacjami zawartymi w zamówieniu zakupu, zaznacz pole wyboru Dopasuj opłaty.
13. Zamknij stronę.


