---
title: Księgowanie zamówienia sprzedaży
description: Ten temat zawiera informacje dotyczące karty Zamówienie sprzedaży na stronie profilu księgowania zapasów.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: 5d84723b51d6977867fa162c4a47befa61bd9ef6
ms.sourcegitcommit: dc3053625dfe24aef64399dd1d002214e7f7619f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755936"
---
# <a name="sales-order-posting"></a>Księgowanie zamówienia sprzedaży

Karta **Zamówienie sprzedaży** na stronie **Profile księgowania** zapasów służy do kontrolowania sposobu księgowania zamówień sprzedaży w księdze głównej. W przypadku zamówienia sprzedaży w księdze głównej są księgowane dwa główne działania: 

- Dokument dostawy
- Faktura

Aby transakcja fizyczna (dokument dostawy) została zaksięgowana w księdze głównej dla zamówienia sprzedaży, muszą być spełnione następujące warunki:

- Na stronie **Parametry zarządzania zapasami i magazynem** musi być zaznaczone pole wyboru **Księguj dokument dostawy w księdze**.
- Na stronie **grupa modeli pozycji** dla pozycji wybranej w **wierszu zamówienia sprzedaży musi być zaznaczone pole wyboru Księguj magazyn fizyczny w księdze**.
- Na stronie **Profil księgowania zapasów** należy określić konta główne następujących typów księgowania:
  - Koszt jednostek, dostarczone
  - Koszt własny sprzedaży, dostarczone

Aby transakcja finansowa (faktura) została zaksięgowana w księdze głównej dla zamówienia sprzedaży, muszą być spełnione następujące warunki:

- Na stronie **grupa modeli pozycji** dla pozycji wybranej w **wierszu zamówienia sprzedaży musi być zaznaczone pole wyboru Księguj magazyn finansowy w księdze**.
- Konta główne muszą być określone na stronie na stronie **Profil księgowania zapasów** dla następujących typów księgowania:
  - Koszt jednostek, zafakturowane
  - Koszt własny sprzedaży, zafakturowany
  - Przychód
  - Rabat\*

> [!NOTE]
> Konto rabatu jest opcjonalne. Wiele przepisów księgowych, takich jak GAAP i IFRS, wymaga, aby rabaty zmniejszały przychody ze sprzedaży, w związku z tym te konta nie są używane w wielu scenariuszach. Jeśli zezwalają na to przepisy lokalne, użyj osobnego konta głównego do zaksięgowania części ceny sprzedaży z rabatem.

Aby podczas generowania dokumentu dostawy dla zamówienia sprzedaży wartość przychodu odroczonego (szacowanego) był księgowana w księdze głównej, muszą być spełnione następujące warunki:

- Na stronie **grupa modeli pozycji** dla pozycji wybranej w **wierszu zamówienia sprzedaży musi być zaznaczone pole wyboru Księguj magazyn fizyczny w księdze**.
- Na stronie **Grupa modeli przedmiotów** musi być zaznaczone pole wyboru **Księgowanie do odroczonego konta przy dostawie przy dostawie**.
- Na stronie **Parametry zarządzania zapasami i magazynem** musi być zaznaczone pole wyboru **Księguj dokument dostawy w księdze**.
- Na stronie **Parametry zarządzania zapasami i magazynem** musi być zaznaczone pole wyboru **Księguj podatek od sprzedaży fizycznej**.
- Na stronie **Parametry rozrachunków z odbiorcami** musi być zaznaczone pole wyboru **Księguj dokument dostawy w księdze**.
- Na stronie **Profil księgowania zapasów** należy określić konta główne następujących typów księgowania:
  - Przychód odroczony przy dostawie
  - Przeciwstawne dla przychodu odroczonego przy dostawie
  - Odroczony podatek przy dostawie

> [!NOTE]
> Zalecane jest włączenie opcji Księguj magazyn **fizyczny** i **Księguj dokument dostawy w księdze**. Włączenie tych opcji może pomóc w szybszej procedury zamykania miesiąca, ponieważ nie trzeba ręcznie obliczać i księgować odroczeń. Ponadto w sprawozdaniach finansowych odroczone kwoty będą automatycznie odzwierciedlane bez ręcznej interwencji.

> [!IMPORTANT]
> Opcja Księguj **na koncie odroczonego przychodu** przy dostawie sprzedaży nie jest używana w przychód. Aby uzyskać więcej informacji o przychód, przejdź do przeglądu [Rozpoznawania przychodów](/accounts-receivable/revenue-recognition-overview.md)

## <a name="sample-posting-profile-configuration"></a>Przykładowa konfiguracja profilu księgowania 

Poniższa tabela pokazuje przykłady domyślnych typów księgowań wraz z przykładowymi kontami głównymi i opisami:
 
- Kolumna **Konto rozliczeniowe** wskazuje typ księgowania jako konto rozliczeniowe. Kwota zaksięgowana na tym koncie jest automatycznie odwracana w momencie zaksięgowania późniejszej transakcji. 
- Kolumna **P/F** wskazuje **P** dla księgowania fizycznego i **F** dla księgowania finansowego. 
- Kolumna **Wykonaj** wskazuje, czy konto główne określonego typu księgowania jest zazwyczaj takie samo jak inny typ księgowania. Wartość w kolumnie wskazuje typ typowo stosowanego księgowania.

> [!NOTE]
> Te konta główne i nazwy kont głównych są tylko sugestiami. Zaleca się, aby współpracować z księgowym, aby ustalić najlepszą konfigurację dla potrzeb firmy.


| Typ księgowania | Przykład konta głównego | Przykład nazwy konta głównego | Typ konta | Uznanie/kredyt? | Konto rozliczeniowe | P/F | Śledzenie | Opis |
|------------|------------------------|-------------------------|--------------|---------|-------------------|------------|------|-------------------------|
| Koszt jednostek, dostarczone | 140100</br>140101 | Zapasy materiałów</br>Materiały wysłane bez faktury | Element zawartości | Środki | Tak | P | Koszt jednostek, zafakturowane | Używane podczas zaksięgowania dokumentu dostawy dla zamówienia sprzedaży. Konto przeciwstawne jest kosztem sprzedanych towarów, dostarczonych. Kwota na tym koncie jest wycofywana po zaksięgowaniu faktury zamówienia sprzedaży. Konto Zapasy materiałów wysłanych, które nie zostały zafakturowane, może być użyte do reprezentowania magazynu fizycznego, a konto zapasów materiałów można zarezerwować na podstawie aktualizacji finansowej. |
| Koszt własny sprzedaży, dostarczone | 500150 | Odroczone KWS | Wydatek | Uznanie | Tak | P  | Używane podczas zaksięgowania dokumentu dostawy dla zamówienia sprzedaży. Potrącenie na konto stanowi Koszt dostarczonych jednostek. Kwota na tym koncie jest wycofywana po zaksięgowaniu faktury zamówienia sprzedaży. |
| Koszt jednostek, zafakturowane | 140100 | Zapasy materiałów | Element zawartości | Środki | Nie | P | Koszt jednostek, dostarczone | Używane, gdy księgowana jest faktura zamówienia sprzedaży. Potrącenie na to konto stanowi Koszt sprzedanych towarów, zafakturowany. To konto reprezentuje zapasy w bilansie. |
| Koszt własny sprzedaży, zafakturowany | 500100 | Materiały KWS | Wydatek | Uznanie | Nie | P  | Używane, gdy księgowana jest faktura zamówienia sprzedaży. Potrącenie na to konto stanowi Koszt jednostek, zafakturowany. To konto reprezentuje KSZ w instrukcji P&amp;L. |
| Przychody (przychody z zamówienia sprzedaży*) | 400100 | Materiały przychodowe | Przychód | Środki | Nie | P   | Używane, gdy księgowana jest faktura zamówienia sprzedaży. Konto przeciwstawne do tego konta jest kontem rozrachunkowym (saldo odbiorcy*) w profilu **księgowania rozrachunków z odbiorcami**. |
| Prowizja (Sprzedaż, prowizja*) | 602150 | Wydatki z tytułu prowizji | Wydatek | Uznanie | Nie | P  | Używane, gdy prowizja jest włączona i obliczana dla sprzedaży oraz księgowana podczas procesu fakturowania zamówienia sprzedaży. Przeciwstawne dla tego konta jest prowizja od zobowiązań. |
| Konto przeciwstawne prowizji (Sprzedaż, Konto przeciwstawne prowizji*) | 201110 | Prowizje naliczone | Pasywa | Środki | Tak | P | Używane, gdy prowizja jest włączona i obliczana dla sprzedaży oraz księgowana podczas procesu fakturowania zamówienia sprzedaży. Potrącenie na tym rachunku stanowi koszt Komisji. |
| Przychód odroczony przy dostawie (Sprzedaż – Przychód dokumentu dostawy*) | 401400 | Naliczona sprzedaż | Przychód | Środki | Tak | P  | Używane, gdy przychód odroczony dla dostawy jest włączony i księgowany podczas przetwarzania dokumentu dostawy zamówienia sprzedaży. Kompensacja dla tego konta jest kompensacją przychodów odroczonych. Kwoty na tym koncie są automatycznie wycofywne po zaksięgowaniu faktury zamówienia sprzedaży. |
| Odroczona kompensacja przychodów przy dostawie (Sprzedaż – kompensacja przychodów z listu przewozowego)* | 130400 | Rozrachunki z odbiorcami — niefakturowane | Element zawartości | Uznanie | Tak | P  | Używane, gdy przychód odroczony dla dostawy jest włączony i księgowany podczas przetwarzania dokumentu dostawy zamówienia sprzedaży. Przesunięciem na tym koncie jest Przychód odroczony w momencie dostawy. Kwoty na tym koncie są automatycznie wycofywne po zaksięgowaniu faktury zamówienia sprzedaży. |
| Odroczony podatek od sprzedaży przy dostawie (sprzedaż, podatek od listu przewozowego*) | 250500 | Odroczony podatek od sprzedaży | Pasywa | Środki | Tak | P  | Używane, gdy jest włączony przychód odroczony dla dostawy i jest włączony podatek fizyczny księgowany. Kwota podatku jest księgowana podczas przetwarzania dokumentu dostawy zamówienia sprzedaży. |

\*Wartości podane w nawiasach w tej tabeli reprezentują wartości używane w polu **Typ księgowania** na stronie **Transakcje z voucherami**. **Typ księgowania** możesz wyświetlić na stronie **Transakcje z voucherami** na karcie **Ogólne**.

## <a name="sales-category-posting"></a>Publikowanie kategorii sprzedaży

Zamiast ustawiać księgowanie zapasów dla wszystkich towarów, grupy towarów lub pojedynczych towarów, można skonfigurować kategorie i kontrolować księgowanie w księdze według kategorii sprzedaży. Aby uzyskać więcej informacji na temat konfigurowania hierarchii kategorii i przypisywania kategorii do produktów, przejdź do [Tworzenie hierarchii klasyfikacji produktów](/supply-chain/pim/tasks/create-hierarchy-product-classification.md) i [Klasyfikuj produkt za pomocą hierarchii kategorii](/supply-chain/pim/tasks/classify-product-category-hierarchies.md).

Po utworzeniu hierarchii kategorii należy przypisać hierarchię do jednego lub większej liczby typów. Aby w zamówieniach sprzedaży użyć hierarchii kategorii, należy przypisać kategorię do typu hierarchii kategorii sprzedaży. Aby uzyskać więcej informacji, przejdź do [Informacje o hierarchiach kategorii](/dynamicsax-2012/appuser-itpro/about-category-hierarchies.md).

## <a name="create-revenue-posting-by-sales-category"></a>Utwórz księgowanie przychodów według kategorii sprzedaży

Aby przypisać księgowania w księdze do zamówienia sprzedaży na podstawie kategorii sprzedaży, należy wykonać następujące czynności:

1. Przejdź do **Zarządzanie zapasami** > **Konfiguracja** > **Księgowanie** > **Księgowanie**.
2. Kliknij kartę **Sprzedaż**.
3. Wybierz przycisk radio dla typu księgowania, który chcesz skonfigurować (na przykład **Przychód**).
4. Wybierz pozycję **Nowy**.
5. W polu **Kod towaru** wybierz **Kategoria**.
6. W polu **Relacja kategorii** wybierz kategorię dla profilu księgowania.
7. W polu **Kod konta** wybierz opcję **Tabela**, **Grupa** lub **Wszystko**. Na przykład, aby zastosować profil księgowania do wszystkich odbiorców, wybierz opcję **Wszystko**.
   - Jeśli wybrałeś **Tabela** w kroku 6, wybierz konkretny **Numer dostawcy** dla profilu księgowania w polu **Relacja konta**.
   - Jeśli wybrałeś **Grupa** w kroku 6, wybierz konkretny **Grupa dostawcy** dla profilu księgowania w polu **Relacja konta**.
   - Jeśli w kroku 6 wybierzesz **Wszystko**, pole **Relacja konta** pozostanie puste.

8. Aby skojarzyć określoną grupę podatku z wybranym typem księgowania, należy wybrać **Grupę podatku**. Jeśli to pole pozostanie puste, dany typ księgowania będzie dotyczyć wszystkich istniejących grup podatków. Księgowanie określone dla grup podatków dotyczy tylko transakcji wykonanych w związku ze sprzedażą i zakupami.

9. W polu **Konto główne** określ numer konta, na które ma być zaksięgowany typ konta. Należy wybrać jeden z numerów kont istniejących w planie kont.
