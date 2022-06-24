---
title: Profile księgowania zapasów
description: Ten artykuł zawiera omówienie profili księgowania zapasów.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cae5b39ef8e6e153fe522dee1874deae2a2cb86e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901350"
---
# <a name="inventory-posting-profiles"></a>Profile księgowania zapasów

[!include [banner](../includes/banner.md)]

Profile księgowania inwentaryzacji kontrolują księgowanie transakcji podrzędnej księgi inwentarzowej do księgi głównej. Transakcje w księdze pomocniczej zapasów mogą być generowane z wielu modułów, takich jak **sprzedaż i marketing**, **zamówienia i zaopatrzenie**, **kontrola produkcji** i wiele innych. Transakcje w księdze pomocniczej zapasów mogą być księgowane za każdym razem, gdy pozycja jest używana w zamówieniu sprzedaży lub zamówieniu zakupu. 

Mogą zostać zaksięgowane dodatkowe transakcje w księdze pomocniczej:
- Za każdym razem, gdy dokument jest aktualizowany.
- Kiedy dokument pakowania zamówienia sprzedaży lub faktura zostają zaksięgowane.
- Kiedy generowany jest rachunek za produkt lub faktura z zamówienia zakupu.

Aby uzyskać więcej informacji, przejdź do rozdziału podarkusza transakcje zapasów.

## <a name="inventory-transaction-overview"></a>Przegląd transakcji na zapasach

Każda transakcja w księdze pomocniczej zapasów zawiera:
 - Ilość 
 - Cena 
 - Witryna 
 - Magazyn 
 - Lokalizacja 

Transakcje w księdze pomocniczej tworzą dwa wpisy w księdze głównej: wpis fizyczny i wpis finansowy. Aby uzyskać więcej informacji, odwiedź stronę [Aktualizacje fizyczne i finansowe](/supply-chain/cost-management/physical-financial-updates.md).
Poniższy przykład to zamówienie zakupu składające się z trzech wierszy. W tym przykładzie załóżmy, że całe zamówienie dotyczy jednego miejsca i magazynu. Każdy wiersz zamówienia zakupu ma jeden powiązany rekord InventTrans - znany też jako transakcja inwentaryzacyjna - i każdy wiersz dotyczy ilości 10 sztuk. Poniższy diagram pokazuje związek jednego nagłówka zamówienia z trzema wierszami zamówienia, z których każdy ma jeden rekord InventTrans.

![Diagram relacji dla zamówienia zakupu z trzema wierszami, z których każdy zawiera jeden rekord InventTrans.](./media/InventTransRelationship.PNG)

W pierwszym wierszu zamówienia otrzymano ilość 5 sztuk. Pełna ilość dla drugiego wiersza i brak ilości otrzymanej w trzecim wierszu zamówienia. Teraz jest druga transakcja inwentaryzacyjna związana z pierwszym wierszem zamówienia zakupu. Transakcja dla drugiej linii zamówienia zakupu zostanie zaktualizowana do **Odebrane**, a trzecia transakcja pozostanie bez zmian. Poniższy schemat przedstawia relację z dodatkowym rekordem InventTrans dla linii 1 zamówienia zakupu.

![Diagram relacji dla zamówienia zakupu z trzema liniami. Jeden wiersz jest częściowo odebrany i zawiera dwa rekordy InventTrans.](./media/InventTransRelationshipPartialReceipt.PNG)

W tym przykładzie do księgi głównej zostanie zaksięgowany voucher; jest to voucher fizyczny. Grupa modelu artykułu jest skonfigurowana do księgowania zapasów fizycznych, a wszystkie artykuły korzystają z tej samej grupy modelu artykułu. Profil księgowania zapasów korzysta z jednego zestawu kont głównych. Zostanie utworzony jeden voucher, a rekord InventTrans będzie łączył zarówno InventTrans 1, jak i InventTrans 2 z tym samym bonem.

Następnie otrzymuje się fakturę za ilość, która została otrzymana w liniach 1 i 2. W księdze głównej tworzony jest kolejny voucher, który jest voucherem finansowym. Grupa modeli pozycji jest skonfigurowana do księgowania inwentaryzacji finansowej. Nowy, drugi voucher jest związany z InventTrans 1 i InventTrans 2.

W zależności od modelu kalkulacji kosztów może istnieć trzecie księgowanie księgi głównej dla transakcji podrzędnej księgi inwentarzowej związanych z zamknięciem i rozliczeniem inwentaryzacji. Aby uzyskać więcej informacji, zobacz [Zamknięcie zapasów](/supply-chain/cost-management/inventory-close.md). Możesz przejrzeć szczegóły wszystkich transakcji inwentaryzacyjnych, przechodząc do **Zarządzanie inwentarzem** > **Pytania i raporty** > **Transakcje**.

>[!Important]
> Transakcje inwentaryzacyjne będą dzielone dla każdej unikalnej kombinacji wymiarów zapasów i dla każdej częściowej aktualizacji. Te informacje przedstawiono w poprzednim przykładzie dla aktualizacji częściowych.

### <a name="split-inventory-based-on-inventory-dimension-example"></a>Podziel zapasy na podstawie wymiaru zapasów: przykład

Wiersz 3 zamówienia zakupu w przykładzie jest pozycją serializowaną. Dziesięć numerów seryjnych jest rejestrowanych w zamówieniu zakupu podczas procesu odbioru. Transakcja inwentaryzacyjna zostanie podzielona na 10 transakcji inwentaryzacyjnych. Poniższy diagram pokazuje relację i dodatkowe transakcje inwentaryzacyjne, każda z własnym numerem seryjnym, związane z wierszem 3 zamówienia zakupu.

![Diagram relacji dla zamówienia zakupu z trzema liniami. Jeden wiersz jest serializowany i pokazuje dodatkowe rekordy InventTrans](./media/InventTransRelationshipSerialNumber.PNG)

W powyższym przykładzie, jeśli każdy numer seryjny jest odbierany w jednym przyjęcia produktów, zostanie utworzony jeden dodatkowy załącznik. Pole vouchera fizycznego będzie powiązane z każdym numerem seryjnym. To samo dotyczy aktualizacji finansowej, gdy wystawiasz fakturę za zamówienie zakupu.

## <a name="inventory-transactions"></a>Transakcje magazynowe

Transakcje inwentaryzacyjne możesz przeglądać na stronie **Transakcje inwentaryzacyjne** w zakładce **Zarządzanie zapasami i magazynem** lub **Zarządzanie kosztami**. Możesz także wyświetlić transakcje inwentaryzacyjne związane z konkretnym wierszem dokumentu źródłowego - np. wierszem zamówienia zakupu lub wierszem zamówienia sprzedaży - wybierając **Zapasy**, a następnie **Transakcje**. 

Strona **Transakcje magazynowe** zawiera następujące pola.

| Pole            | Opis                                 |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------|
| Numer towaru      | Numer pozycji związanej z transakcją.                                                                  |
| Data fizycznej transakcji    | Data przybycia zapasów do magazynu, opuszczenia magazynu, zużycia w produkcji lub wyprodukowania. Na przykład, data delegowania na
dokumencie dostawy dla zamówienia sprzedaży lub dokumentu przyjęcia produktu dla zamówienia zakupu.                             |
| Data finansowa   | Dzień, w którym transakcja zapasów zostaje zamknięta, a koszt zapisany w księdze głównej. Na przykład data zaksięgowania na fakturze 
wygenerowanej z zamówienia sprzedaży lub zakupu. Aktualizacja dokumentu referencyjnego nie jest dozwolona po uzupełnieniu daty finansowej. |
| Odwołanie        | Wskazuje źródło transakcji oraz typ dokumentu, który jest wyświetlany w polu **Liczba**. Na przykład: zamówienie sprzedaży, zamówienie zakupu lub potwierdzenie zlecenia przelewu.                                                 |
| Identyfikator           | Wskazuje identyfikator referencyjny dla transakcji. Jeśli na przykład pole **Odwołanie** wskazuje zamówienie sprzedaży, w polu **Liczba** jest wskazywany numer zamówienia sprzedaży.                                                       |
| Odbiór (status) | Dla transakcji inwentaryzacyjnych, które są odbiorem, pole to określa status pokwitowania. Na przykład zamówienie zakupu jest pokwitowaniem, a jego status może być **Zamówione** lub **Zakupione**.                                                            |
| Wydanie (status)   | Dla transakcji zapasów, które są wydaniami, pole to określa status wydania. Na przykład zamówienie sprzedaży jest sprawą, a jego status może być **Zamówione** lub **Sprzedane**.                         |
| Ilość         | Ilość transakcji zapasów. W przypadku przychodów do magazynu używane są wartości dodatnie, natomiast dla przychodów z magazynu są używane wartości ujemne.                                                                                                                          |
| Jednostka             | Jednostka miary, w której wyrażona jest wielkość.                                                                                   |
| Ilość efektywna      | Ilość masy połowowej dla transakcji. Aby uzyskać więcej informacji, przejdź do [O produktach w ilości efektywnej](/dynamicsax-2012/appuser-itpro/about-catch-weight-items.).       |
| Jednostka ilości efektywnej          | Jednostka miary ilości efektywnej, w której wyrażona jest ilość efektywna.                                                         |
| Kwota kosztów      | Ostateczny koszt transakcji inwentaryzacyjnej. To pole jest uzupełniane, gdy transakcja jest aktualizowana finansowo. W zależności od metodologii kalkulacji kosztów, proces zamknięcia i korekty zapasów może zaktualizować to pole.                            |

## <a name="inventory-status"></a>Stan zapasów

Każda transakcja inwentaryzacyjna ma status, który jest wyświetlany w polu **Przyjęcie** lub **Wydanie**. Pole, które jest używane, zależy od rodzaju transakcji zapasów. Wpływy to transakcje, które zwiększają stan zapasów. Na przykład zamówienie zakupu z ilością dodatnią lub zwrot zamówienia sprzedaży z ilością ujemną. Wydania to transakcje inwentaryzacyjne, które zmniejszyły stan inwentarza. Na przykład zamówienie sprzedaży z ilością dodatnią lub zwrot zamówienia zakupu z ilością ujemną.

### <a name="receipt-status"></a>Stan przychodu

Poniższa tabela opisuje status **Odbioru**.

| **Stan przychodu** | **opis**       |
|--------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| Zamówiona            | Początkowy status każdej transakcji zapasów, która stanowi odbiór. Dotyczy to zamówień zakupu z dodatnią ilością, zamówień produkcyjnych oraz zwrotów zamówień sprzedaży z ujemną ilością.                                                   |
| Zarejestrowano         | Ten status jest używany, gdy stosowany jest dwuetapowy proces przyjmowania towaru lub gdy status przybycia towaru jest używany do wskazania, że produkt został dostarczony. Używa się go, gdy numery partii lub serii są "przypisywane" lub rejestrowane do zamówienia. Aby uzyskać więcej informacji na temat przybycia przedmiotu, przejdź do [Przegląd przybycia](/supply-chain/inventory/arrival-overview.md). |
| Odebrane           | Ten status jest używany, gdy transakcja jest fizycznie aktualizowana. W przypadku zamówienia zakupu jest to moment zaksięgowania potwierdzenia odbioru produktu. W przypadku zwrotu zamówienia sprzedaży jest to moment zaksięgowania dokumentu dostawy.                                                                            |
| Zakupione          | Ten status jest używany, gdy transakcja jest finansowo aktualizowana. W przypadku zwrotu zamówienia zakupu lub sprzedaży jest to moment, w którym generowana jest faktura.                                                                                             |

### <a name="issue-status"></a>Stan rozchodu

Poniższa tabela opisuje status **Wydania**.

| **Stan rozchodu**  | **opis**            |
|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| Zamówione          | Początkowy status każdej transakcji zapasów, która stanowi wydanie. Dotyczy to zamówień sprzedaży z dodatnią ilością, zamówień produkcyjnych BOM lub linii recepturowych oraz zwrotów z zamówień zakupu z ujemną ilością.                                             |
| Zamówione zarezerwowane  | Ten stan zapasów wskazuje, że ssą zarezerwowane dla zamówienia, które zostało utworzone, ale jeszcze fizycznie nie wpłynęło do magazynu. Gdy inwentarz zostanie odebrany, jego status automatycznie zmieni się na **Zarezerwowane fizycznie**. Aby uzyskać więcej informacji o rezerwacjach, przejdź na stronę [Rezerwacje ilości zapasów](/supply-chain/inventory/reserve-inventory-quantities.md). |
| Fizycznie zarezerwowane | Ten status oznacza, że zapasy zostały przydzielone lub zarezerwowane dla konkretnego zamówienia. Kiedy towar jest zarezerwowany, nie jest fizycznie dostępny dla innych zamówień.                                 |
| Pobrany         | Oznacza to, że towar został pobrany z magazynu. Zapasy nadal fizycznie znajdują się w magazynie, nie zostały usunięte, ale nie są dostępne dla innych zamówień.  |
| Wydane          | Ten status jest używany, gdy transakcja jest fizycznie aktualizowana. W przypadku zamówienia sprzedaży jest to moment zaksięgowania dowodu pakowania; w przypadku zwrotu zamówienia zakupu jest to moment zaksięgowania potwierdzenia odbioru produktu.                                                                      |
| Sprzedane              | Jest to status używany, gdy transakcja jest aktualizowana finansowo. W przypadku zlecenia zakupu lub zlecenia sprzedaży jest to moment, w którym generowana jest faktura.|

Aby uzyskać więcej informacji na temat transakcji inwentaryzacyjnych, przejdź do [Szczegóły transakcji inwentaryzacyjnych](/supply-chain/inventory/inventory-transactions-details.md).

## <a name="configure-an-inventory-posting-profile"></a>Skonfiguruj profil księgowania zapasów

Aby skonfigurować profil księgowania zapasów, wykonaj poniższe kroki:

1.  Otwórz: **Zarządzanie zapasami** > **Konfiguracja** > **Księgowanie** > **Księgowanie**.
2.  Wybierz zakładkę odpowiadającą rodzajowi transakcji. Na przykład wybierz **Zlecenie zakupu**.
3.  Wybierz przycisk radiowy dla typu postu. Na przykład wybierz **Wydatki na zakup jako wydatek**.
4.  Wybierz pozycję **Nowy**.
5.  W polu **Kod elementu** wybierz opcję **Tabela**, **Grupa**, **Wszystko** lub **Kategoria**. Na przykład, aby skonfigurować profil delegowania dla konkretnej grupy artykułów, wybierz **Grupa**.
     - Jeśli wybrałeś **Tabela** w kroku 5, wybierz konkretny Numer elementu dla profilu księgowania w polu **Relacja elementu**.
     - Jeśli wybrałeś **Grupa** w kroku 5, wybierz konkretny **Grupa elementu** dla profilu księgowania w polu **Relacja elementu**.
     - Jeśli w kroku 5 wybierzesz **Wszystko**, pole **Relacja elementu** pozostanie puste.
     - Jeśli w kroku 5 wybierzesz **Kategoria**, pole **Relacja elementu** pozostanie puste. W polu **Relacja kategorii**, aby wybrać kategorię, do której odnosi się profil postu.

6.  W polu **Kod konta** wybierz opcję **Tabela**, **Grupa** lub **Wszystko**. Na przykład, aby zastosować profil księgowania do wszystkich dostawców, wybierz opcję **Wszystko**.
     - Jeśli wybrałeś **Tabela** w kroku 5, wybierz konkretny numer dostawcy dla profilu księgowania w polu **Relacja konta**.
     - Jeśli wybrałeś **Grupa** w kroku 5, wybierz konkretny grupa dostawcy dla profilu księgowania w polu **Relacja konta**.
     - Jeśli w kroku 5 wybierzesz **Wszystko**, pole **Relacja konta** pozostanie puste.

7.  Aby skojarzyć określoną grupę podatku z wybranym typem księgowania, należy wybrać **Grupę podatku**. Jeśli to pole jest puste, typ księgowania ma zastosowanie do wszystkich istniejących grup podatkowych. Księgowanie, które jest określone dla grup podatkowych, dotyczy tylko transakcji sprzedaży i zakupów.
8.  Określ numer konta, które ma zostać zaksięgowane jako typ konta w polu **Konto główne**. Jeśli numer konta nie został jeszcze utworzony jako typ księgowości, możesz utworzyć nowe konto. Nowe konto można utworzyć na stronie **szczegółów konta głównego** w księdze głównej.

## <a name="additional-resources"></a>Dodatkowe zasoby

Każda zakładka na stronie **Profilu księgowania zapasów** odnosi się do księgi pomocniczej w Dynamics 365 Supply Chain Management. Aby uzyskać więcej informacji, zobacz:
-   [Księgowanie zamówienia sprzedaży](sales-order-posting.md)
-   [Księgowanie zamówienia zakupu](purchase-order-posting.md)
-   [Księgowanie zapasów](inventory-posting.md)
-   [Księgowanie kontroli produkcji](production-posting.md)
-   [Księgowanie odchylenia kosztów standardowych](standard-cost-variance-posting.md)
