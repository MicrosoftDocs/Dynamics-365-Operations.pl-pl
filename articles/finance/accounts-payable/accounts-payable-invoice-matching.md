---
title: Omówienie uzgadniania rozrachunków z dostawcami
description: Uzgadnianie faktur rozrachunków z dostawcami jest procesem uzgadniania obejmującym informacje z faktury dostawcy, zamówienia zakupu i przyjęć produktów.
author: abruer
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoicePostingHistory
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 27361
ms.assetid: 9f3dace7-05d8-4974-8f85-aca2e224876c
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a8e283038a0cc1c9834a827c453f2951e9e87bcf
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446886"
---
# <a name="accounts-payable-invoice-matching-overview"></a>Omówienie uzgadniania rozrachunków z dostawcami

[!include [banner](../includes/banner.md)]

Uzgadnianie faktur rozrachunków z dostawcami jest procesem uzgadniania obejmującym informacje z faktury dostawcy, zamówienia zakupu i przyjęć produktów.

Podczas uzgadniania dokumentów różnice między tymi dokumentami są nazywane rozbieżnościami (w uzgadnianiu/wykrytymi podczas uzgadniania). Rozbieżności w uzgadnianiu są porównywane z ustawionymi wartościami tolerancji. Jeśli rozbieżność przekracza wartość procentową lub kwotową, są wyświetlane ikony uzgadniania odchyleń na stronach Faktura od dostawcy i Historia faktur i szczegóły ich uzgadniania. 

Załóżmy, że wprowadzasz zamówienie zakupu z jednym wierszem towaru dotyczącym 1000 baterii po cenie jednostkowej 1,00. Zamówienie zakupu zostaje zatwierdzone i wysłane do dostawcy. Dostawca wysyła 1000 baterii i wprowadzasz dokument przyjęcia 1000 baterii po cenie jednostkowej 1,00. Koszt magazynowy baterii jest aktualizowany o tę cenę. 

Jest dostarczana faktura na 1000 baterii po cenie jednostkowej 1,10. Wedle zasad firmy w przypadku towaru tej kategorii jest dopuszczalna 5-procentowa rozbieżność. Zatem cena 1,05 mieściłaby się w tych granicach, ale cena 1,10 już jest niedopuszczalna. Podczas wprowadzania danych faktury wykrywana jest rozbieżność uzgadniania cen i można zapisać fakturę w oczekiwaniu na rozwiązanie sprawy rozbieżności.

Można użyć następujących typów uzgadniania faktur w rozliczeniach z dostawcami:

-   Uzgodnienie sum faktur — uzgadnianie sum na fakturze z sumami na zamówieniu zakupu. Ten typ uzgadniania faktury zawiera najmniej szczegółów, pozwala więc wybrać opcje kontroli maksymalnie skracające czas weryfikacji informacji o uzgadniania faktur.
-   Uzgadnianie dwuelementowe — uzgadnianie informacji o cenie na fakturze z informacjami o cenie na zamówieniu zakupu.
-   Uzgadnianie trzyelementowe — uzgadnianie informacji o cenie na fakturze z informacjami o cenie na zamówieniu zakupu. Pozwala też uzgadniać informacje o ilości na fakturze z informacjami o ilości na dokumentach przyjęcia produktów wybranych dla faktury.
-   Uzgadnianie opłat — uzgadnianie informacji o opłatach (kwotach) na fakturze z informacjami o opłatach (kwotami) zamówieniu zakupu.

> [!NOTE]
> Inne formy weryfikacji faktury można realizować za pomocą zasad faktur od dostawców. 

Uzgadnianie dwuelementowe i trzyelementowe zawsze uzgadnia informacje o cenie na podstawie ceny jednostki. Za pomocą tych zasad można też uzgadniać informacje o cenach według ceny całkowitej.
-   Uzgadnianie ceny jednostkowej netto — dopasowywanie informacji dla uzgadniania dwu- i trzyelementowego przez porównywanie ceny jednostkowej netto dla każdego wiersza z odpowiednia ceną jednostkową netto na zamówieniu zakupu. Cena jednostkowa netto jest określana według następującego wzoru: kwota netto wiersza / ilość w wierszu
-   Uzgodnienie cen całkowitych — dopasowywanie informacji dla uzgadniania dwu- i trzyelementowego przez porównywanie ceny jednostkowej netto dla każdego wiersza z odpowiednia kwotą netto na zamówieniu zakupu. Kwota netto jest określana według następującego wzoru: *(cena jednostkowa \* ilość w wierszu) + opłaty za wiersze - rabaty wiersza*. Podczas uzgadniania cen całkowitych według wartości procentowej system porównuje wartości w walucie transakcji. Podczas uzgadniania cen całkowitych według kwoty system porównuje wartości w walucie rozliczeniowej.

Na ogół obliczenia związane z uzgadnianiem faktur są wykonywane automatycznie podczas edytowania faktur od dostawcy na stronie Faktura od dostawcy. Ewentualnie uzgadnianie faktur może być wykonywane na żądanie, jeśli jest taka potrzeba. Uzgadnianie faktur na żądanie jest kontrolowane dla firmy za pomocą opcji Automatycznie aktualizuj stan nagłówka faktury na stronie Parametry modułu rozrachunków z dostawcami na karcie Weryfikacja faktury. Uzgadnianie faktury może być również wykonane w ramach procesu przeglądania faktury. Można wyświetlić wyniki uzgadniania faktury na stronie Faktura od dostawcy i na pokrewnych stronach uzgadniania faktur.

## <a name="invoice-totals-matching"></a> Uzgadnianie sum faktur
Uzgadnianie sum faktury może pomóc zagwarantować, że rozbieżność sum faktury i kwot oczekiwanych nie wykracza poza dopuszczalne limity tolerancji. Na stronie Szczegóły uzgadniania faktur porównywanych jest sześć sum (patrz tabela). Jeśli dopuszczalna tolerancja dla uzgadniania sum faktury wynosi 20%, wartość procentowa odchylenia 100% dla łącznej kwoty rabatu jest uznawana za rozbieżność.

| Pole Łącznie:    | Rzeczywista suma faktury | Oczekiwana suma faktury | Procent odchylenia | Stan uzgadniania |
|----------------|----------------------|------------------------|---------------------|--------------|
| Saldo        | 495,00               | 495,00                 | 0%                  | Powodzenie       |
| Rabat końcowy | 0,00                 | 9,90                   | 100%                | Błąd       |
| Opłaty        | 64,90                | 64,90                  | 0%                  | Powodzenie       |
| Podatek      | 139,98               | 137,50                 | 2%                  | Powodzenie       |
| Zaokrąglenie      | 0,00                 | 0,00                   | 0%                  | Powodzenie       |
| Kwota faktury | 699,88               | 687,50                 | 2%                  | Powodzenie       |

Uzgadnianie sum faktury dla firmy jest kontrolowane za pomocą pola Dopasuj sumy faktur na stronie Parametry modułu rozrachunków z dostawcami. Uzgadnianiu podlegają oczekiwane i rzeczywiste sumy faktur. Oczekiwane sumy faktur są obliczane na podstawie informacji o cenach, opłatach i podatkach z zamówienia zakupu i ilości z faktury.

## <a name="two-way-price-totals-matching"></a> Dwuelementowe uzgadnianie cen całkowitych
Za pomocą uzgadniania dwuelementowego można sprawdzić, czy odchylenie między informacjami o cenie w zamówieniu zakupu i na fakturze mieści się w dopuszczalnych granicach tolerancji. Istnieje możliwość porównania informacji o cenie netto każdego wiersza na fakturze oraz wszystkich oczekujących i wcześniej zaksięgowanych wierszy faktury z kwotą netto w odpowiednim wierszu zamówienia zakupu. Taki proces jest nazywany uzgadnianiem cen całkowitych. 

Uzgodnienie cen całkowitych może być oparte na wartości procentowej, kwocie lub wartości procentowej i kwocie. 

Jeśli określono procent tolerancji dla całkowitej ceny zakupu, porównywanych jest pięć pól, jak pokazano w tabeli poniżej. Ponieważ procent tolerancji całkowitej ceny zakupu wynosi 10%, 50% odchylenia ceny całkowitej jest uznawane za rozbieżność.

| Stan uzgadniania | Kwota netto faktury | Oczekiwana kwota netto | Nieuzgodniona całkowita cena zakupu (kwota odchylenia) | Procent nieuzgodnionych całkowitych cen zakupu (procent odchylenia) | Procent tolerancji całkowitej ceny zakupu |
|--------------|--------------------|---------------------|--------------------------------------------------|-----------------------------------------------------------------|----------------------------------------|
| Powodzenie       | 105,00 zł             | 100,00              | 5,00                                             | 5%                                                              | 10%                                    |
| Błąd       | 150,00             | 100,00              | 50,00                                            | 50%                                                             | 10%                                    |

Jeśli określono kwotę tolerancji dla całkowitej ceny zakupu, porównywanych jest pięć pól, jak pokazano w tabeli poniżej. Ponieważ kwota tolerancji całkowitej ceny zakupu wynosi 100,00, wartość odchylenia od ceny całkowitej na poziomie 105,00 jest uznawana za rozbieżność.

| Stan uzgadniania | Kwota netto faktury | Oczekiwana kwota netto | Nieuzgodniona całkowita cena zakupu (kwota odchylenia) | Nieuzgodniona całkowita cena zakupu w walucie rozliczeniowej (kwota odchylenia) | Tolerancja całkowitej ceny zakupu |
|--------------|--------------------|---------------------|--------------------------------------------------|-------------------------------------------------------------------------|--------------------------------|
| Powodzenie       | 150,00             | 100,00              | 50,00                                            | 50,00                                                                   | 100,00                         |
| Błąd       | 205,00             | 100,00              | 105,00 zł                                           | 105,00 zł                                                                  | 100,00                         |

Jeśli dla uzgadnianie całkowitych cen ustawiono tolerancję procentową i kwotową (kwota nieprzekraczalna), obie tolerancje są brane pod uwagę przy ocenie, czy w wierszu występuje rozbieżność uzgadniania. Jeśli wartość procentowa lub kwotowa przekroczy próg tolerancji, tak jak w wierszach 150,00 i 205, 00 w poniższej tabeli, oznacza to, że w wierszu występuje rozbieżność.

| Stan uzgadniania | Kwota netto faktury | Oczekiwana kwota netto | Procent nieuzgodnionych całkowitych cen zakupu (procent odchylenia) | Procent tolerancji całkowitej ceny zakupu | Nieuzgodniona całkowita cena zakupu w walucie rozliczeniowej (kwota odchylenia) | Tolerancja całkowitej ceny zakupu |
|--------------|--------------------|---------------------|-----------------------------------------------------------------|----------------------------------------|-------------------------------------------------------------------------|--------------------------------|
| Powodzenie       | 105,00 zł             | 100,00              | 5%                                                              | 10%                                    | 5,00                                                                    | 100,00                         |
| Błąd       | 150,00             | 100,00              | 50%                                                             | 10%                                    | 50,00                                                                   | 100,00                         |
| Błąd       | 205,00             | 100,00              | 105%                                                            | 10%                                    | 105,00 zł                                                                  | 100,00                         |

Uzgadnianie dwuelementowe jest kontrolowane dla firmy za pomocą pola Zasady uzgadniania wierszy na stronie Parametry modułu rozrachunków z dostawcami. W zależności od wyboru dokonanego w polu Zezwalaj na zastępowanie zasad uzgadniania można wybrać uzgadnianie dwuelementowe dla określonego dostawcy, towaru lub kombinacji dostawcy i towaru na stronie Zasady uzgadniania i dla konkretnego zamówienia zakupu na stronie Zamówieni zakupu.

Uzgadnianie cen całkowitych dla firmy jest kontrolowane za pomocą pola Dopasuj ceny całkowite na stronie Parametry modułu rozrachunków z dostawcami. Na tej stronie określa się również tolerancje procentową i kwotową całkowitej ceny zakupu (kwota nieprzekraczalna).

## <a name="two-way-net-unit-price-matching"></a> Dwuelementowe dopasowanie ceny jednostki netto
Za pomocą uzgadniania dwuelementowego można sprawdzić, czy odchylenie między informacjami o cenie w zamówieniu zakupu i na fakturze mieści się w dopuszczalnych granicach tolerancji. Można porównać informacje o cenie dla jednostkowej ceny netto każdej pozycji na fakturze. Taki proces jest nazywany uzgadnianiem ceny całkowitej netto. 

Na stronie Szczegóły uzgadniania faktur porównywanych jest dziewięć kwot wiersza (patrz tabela). Jeśli dopuszczalna tolerancja cenowa dla uzgadniania ceny jednostkowej netto wynosi 10%, odchylenie 22,61% dla ceny jednostkowej netto jest uznawane za rozbieżność.

| Pola wiersza                    | Wartość faktury | Wartość zamówienia zakupu | Procent odchylenia | Stan uzgadniania |
|-------------------------------|---------------|----------------------|---------------------|--------------|
| Cena jednostkowa                    | 55,40         | 55,38                | 0%                  | Powodzenie       |
| Jednostka cenowa                    | 1,00          | 1,00                 | 0%                  | Powodzenie       |
| Opłaty związane z zakupami          | 50,00         | 0,00                 | 100%                | Błąd       |
| Rabat                      | 0,00          | 0,00                 | 0%                  | Powodzenie       |
| Procent rabatu              | 0,00          | 0,00                 | 0%                  | Powodzenie       |
| Rabat wspólny            | 0,00          | 0,00                 | 0%                  | Powodzenie       |
| Procent rabatu wspólnego | 0,00          | 0,00                 | 0%                  | Powodzenie       |
| Kwota netto                    | 271,60        | 221,52               | 22,61%              | Błąd       |
| Cena jednostkowa netto                | 67.9000       | 55.3800              | 22,61%              | Błąd       |

Uzgadnianie dwuelementowe jest kontrolowane dla firmy za pomocą pola Zasady uzgadniania wierszy na stronie Parametry modułu rozrachunków z dostawcami. W zależności od wyboru dokonanego w polu Zezwalaj na zastępowanie zasad uzgadniania można wybrać uzgadnianie dwuelementowe dla określonego dostawcy, towaru lub kombinacji dostawcy i towaru na stronie Zasady uzgadniania i dla konkretnego zamówienia zakupu na stronie Zamówieni zakupu. 

Uzgadnianie ceny jednostkowej netto dla firmy jest kontrolowane za pomocą pola Włącz weryfikację uzgadniania faktur na stronie Parametry modułu rozrachunków z dostawcami. Wartości tolerancji procentowej dla ceny jednostkowej netto dla towarów, grup towarów, dostawców, grup dostawców, kombinacji towarów i dostawców lub firm można ustawić na stronie Rozbieżności cenowe.

## <a name="two-way-price-totals-matching-and-net-unit-price-matching"></a> Dwuetapowe uzgadnianie cen całkowitych i uzgadniania ceny jednostkowej netto
Uzgadnianie cen całkowitych i uzgadniania ceny jednostkowej netto może być stosowane jednocześnie. W tym przykładzie zakładamy następującą konfigurację:

-   Tolerancja uzgadniania ceny jednostkowej netto dla towaru Napęd USB wynosi 10%.
-   Tolerancja uzgadniania cen całkowitych dla firmy wynosi 15% lub 500,00.

Zamówienie zakupu zawiera następujący wiersz.

| Numer pozycji | Ilość | Cena jednostkowa | Kwota netto |
|-------------|----------|------------|------------|
| Napęd USB   | 1 000    | 10,00      | 10,000.00  |

Wprowadzane są trzy faktury, jak pokazano w poniższej tabeli. Występuje rozbieżność uzgadniania faktury dla Faktury 3, ponieważ odchylenie 1880,00 przekracza próg tolerancji kwotowej dla całkowitej ceny zakupu, który wynosi 500,00. Na potrzeby uzgodnienia cen całkowitych kwota netto faktury obejmuje wszystkie wcześniej zafakturowane faktury oprócz faktury, która jest aktualnie przetwarzana.

| Numer pozycji          | Ilość | Cena jednostkowa | Kwota netto | Zgodność cen | Uzgadnianie cen całkowitych |
|----------------------|----------|------------|------------|-------------|-------------------|
| Faktura 1: Napęd USB | 800      | 10,80      | 8640,00   | Powodzenie      | Powodzenie            |
| Faktura 2: Napęd USB | 100      | 10,80      | 1080,00   | Powodzenie      | Powodzenie            |
| Faktura 3: Napęd USB | 200      | 10,80      | 2160,00   | Powodzenie      | Błąd            |
| Suma                |          |            | 11 880,00  |             |                   |

## <a name="three-way-matching"></a>Uzgadnianie trzyelementowe

Uzgadnianie trzyelementowe pozwala zapewnić, że odchylenie między informacjami o cenie w zamówieniu zakupu i na fakturze mieści się w dopuszczalnych granicach tolerancji, a także, że ilości na fakturze odpowiada ilości w odpowiednich dokumentów przyjęcia produktów.

Porównywane są te same kwoty wiersza na stronie Szczegóły uzgadniania faktur co w przypadku uzgadniania dwuelementowego. Oprócz tego ilość na fakturze jest uzgadniana z ilościami na dokumentach przyjęcia produktów, które zostały odebrane. Jeśli ilość na fakturze różni się od ilości na dokumencie przyjęcia produktów, oznacza to, że wystąpił błąd uzgadniania ilości.

| Pola wiersza                    | Wartość faktury | Wartość zamówienia zakupu | Procent odchylenia | Stan uzgadniania |
|-------------------------------|---------------|----------------------|---------------------|--------------|
| Cena jednostkowa                    | 55,40         | 55,38                | 0%                  | Powodzenie       |
| Jednostka cenowa                    | 1,00          | 1,00                 | 0%                  | Powodzenie       |
| Opłaty związane z zakupami          | 50,00         | 0,00                 | 100%                | Błąd       |
| Rabat                      | 0,00          | 0,00                 | 0%                  | Powodzenie       |
| Procent rabatu              | 0,00          | 0,00                 | 0%                  | Powodzenie       |
| Rabat wspólny            | 0,00          | 0,00                 | 0%                  | Powodzenie       |
| Procent rabatu wspólnego | 0,00          | 0,00                 | 0%                  | Powodzenie       |
| Kwota netto                    | 271,60        | 221,52               | 22,61%              | Błąd       |
| Cena jednostkowa netto                | 67.9000       | 55.3800              | 22,61%              | Błąd       |

| Pola wiersza                     | Wartość faktury | Stan uzgadniania |
|--------------------------------|---------------|--------------|
| Ilość fakturowana               | 4,00          |              |
| Łącznie dopasowanych dokumentów przyjęcia produktów | 0,00          | Błąd       |

Uzgadnianie trzyelementowe jest kontrolowane dla firmy za pomocą pola Zasady uzgadniania wierszy na stronie Parametry modułu rozrachunków z dostawcami. W zależności od wyboru dokonanego w polu Zezwalaj na zastępowanie zasad uzgadniania można wybrać uzgadnianie trzyelementowe dla określonego dostawcy, towaru lub kombinacji dostawcy i towaru na stronie Zasady uzgadniania i dla konkretnego zamówienia zakupu na stronie Zamówieni zakupu.

## <a name="charges-matching"></a> Uzgadnianie opłat
Uzgadnianie opłat może pomóc zagwarantować, że rozbieżność opłat i kwot oczekiwanych nie wykracza poza dopuszczalne procentowe limity tolerancji. Sumy dla każdego kodu opłat mającego zastosowanie do faktury i zamówienia zakupu są porównywane na stronie Porównaj wartości dotyczące opłat — faktura:, jak pokazano w poniższej tabeli. Jeśli dopuszczalna tolerancja dla kodu opłat wynosi 25%, wartość procentowa odchylenia 99 999 999 999,99% dla kodu opłat za Licencję jest uznawana za rozbieżność.

> [!NOTE] 
> Procent odchylenia 99 999 999 999,99% oznacza, że oczekiwana kwota na podstawie zamówienia zakupu wynosi zero, a rzeczywista kwota na fakturze jest wartością dodatnią. 

| Stan uzgadniania opłat | Kod opłat faktury | Rzeczywista całkowita obliczona wartość | Oczekiwana całkowita obliczona wartość | Kwota odchylenia | Procent odchylenia | Dozwolona wartość procentowa rozbieżności |
|----------------------|----------------------|-------------------------------|---------------------------------|-----------------|---------------------|----------------------|
| Błąd               | Licencja              | 25                            | 0                               | 25              | 99 999 999 999,99%  | 25%                  |
| Powodzenie               | Transport              | 200                           | 200                             | 0               | 0%                  | 25%                  |
| Błąd               | Przyspieszone             | 4                             | 2                               | 2               | 100%                | 25%                  |

Uzgadnianie opłat dla firmy jest kontrolowane za pomocą pola Dopasuj opłaty na stronie Parametry modułu rozrachunków z dostawcami. Można skonfigurować procent odchylenia wartości dla opłat na stornie Dozwolone rozbieżności opłat.

> [!NOTE]
> Uzgadniania opłat jest wykonywane tylko dla kodów opłat, dla których opcja Porównaj wartości zamówienia zakupu i faktury na stronie Kod opłat została włączona.

## <a name="related-functionality"></a> Funkcje powiązane
Faktury dostawców często są oparte na dokumentach przyjęcia produktów odpowiadających rzeczywistym wysyłkom, a nie wartościom na zamówieniach zakupu. Czasem zafakturowane kwoty nie zgadzają się z kwotami na zamówieniach zakupu, a niekiedy wysłane ilości nie zgadzają się z ilościami zafakturowanymi. Zarządzanie tymi informacjami można uprościć w następujący sposób:
-   Utwórz fakturę od dostawcy na podstawie dokumentów przyjęcia produktów. Dokumenty przyjęcia produktów są automatycznie proponowane dla faktur i możesz wybrać, które dokumenty przyjęcia mają zostać użyte. W razie potrzeby można też wybrać określoną pozycję w dokumencie przyjęcia produktów dla wielu zamówień zakupu.
-   Przeglądanie i zatwierdzanie rozbieżności między zafakturowanymi ilościami a ilością otrzymaną zgodnie z dokumentem przyjęcia produktów. Jeśli wystąpi różnica, to można zapisać fakturę i później uzgodnić ją z innym dokumentem przyjęcia produktów lub zmienić ilość na fakturze, aby zgadzała się z ilością otrzymaną.
-   Wprowadzanie kwot faktur nieuwzględnionych w oryginalnym zamówieniu zakupu, tak aby dane z faktury były zgodne z fakturą otrzymaną od dostawcy. Można porównywać opłaty w zamówieniach zakupu z opłatami w fakturach. W razie potrzeby można dodać opłaty do faktur i przydzielić je do wierszy faktur.
-   Przeglądanie i zatwierdzanie rozbieżności przy uzgadnianiu rozbieżności cen występujących między ceną jednostkową netto z faktury a ceną jednostkową netto z zamówienia zakupu. Można skonfigurować dozwolone wartości procentowe dla firm, dostawców i towarów. Jeśli cena wiersza faktury dostawcy nie mieści się w dopuszczonym zakresie cen, można zapisać fakturę i czekać na jej zatwierdzenie przed zaksięgowaniem lub na dostarczenie korekty przez dostawcę.

Aby uzyskać więcej informacji, zobacz [Trzyelementowe zasady uzgadniania](three-way-matching-policies.md) i [Konfigurowanie sprawdzania uzgadniania faktur rozrachunków z dostawcami](tasks/set-up-accounts-payable-invoice-matching-validation.md). 




