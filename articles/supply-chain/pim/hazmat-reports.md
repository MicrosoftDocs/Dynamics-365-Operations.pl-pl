---
title: Zapytania i raporty dotyczące materiałów niebezpiecznych
description: W tym artykule wyjaśniono, jak pracować z różnymi raportami związanymi z materiałami niebezpiecznymi. Wiele z tych raportów jest wymaganych w celu zachowania zgodności z różnymi przepisami dotyczącymi materiałów niebezpiecznych podczas przesyłki i magazynowania.
author: t-benebo
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 784361f4e715921890ecff784b62935988732464
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335174"
---
# <a name="hazardous-materials-inquiries-and-reports"></a>Zapytania i raporty dotyczące materiałów niebezpiecznych

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management zapewnia różne raporty związane z materiałami niebezpiecznymi. Wiele z tych raportów jest wymaganych w celu zachowania zgodności z różnymi przepisami dotyczącymi materiałów niebezpiecznych podczas przesyłki i magazynowania.

Wszystkie te raporty, z wyjątkiem raportu dot. **Towarów niebezpiecznych z wieloma metodami**, używają metody dostawy zdefiniowanej dla wysyłki, aby znaleźć rozporządzenie, które powinno być używane do drukowania tekstu wysyłki towarów. Typ transportu jest także skojarzony z przewoźnikiem i usługą przewozu. Dlatego należy skonfigurować firmę przewozową i usługę przewozową oraz połączyć je z trybem dostawy. Metoda dostawy jest związana z rozporządzeniem w sprawie materiałów niebezpiecznych.

Na poniższej ilustracji przedstawiono sekwencję działań, które mają miejsce, gdy system generuje raporty dotyczące materiałów niebezpiecznych.

![Sekwencja działań dla raportów dot. materiałów niebezpiecznych.](media/hazmat-report-sequence.png "Sekwencja działań dla raportów dot. materiałów niebezpiecznych")

## <a name="set-up-hazardous-materials-reporting"></a><a name="set-up"></a>Ustawianie raportów dot. materiałów niebezpiecznych

Zazwyczaj, jeśli towary zawierają materiały niebezpieczne, należy wygenerować określone raporty, które pomogą zachować bezpieczeństwo i przestrzegać przepisów dotyczących materiałów niebezpiecznych. Aby skonfigurować raporty, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**.
2. Otwórz kartę **Raporty**. Na skróconej karcie **Parametrów raportu dot. materiałów niebezpiecznych** należy określić następujące pola.

    | Sekcja | Pole | opis |
    |---|---|---|
    | Towary niebezpieczne z wieloma metodami | Kod przepisu | Umożliwia wybranie rozporządzenia, które będzie używane podczas generowania raportu dot. **Towarów niebezpiecznych z wieloma metodami**. |
    | Limity zapasów materiałów niebezpiecznych | Kod przepisu | Umożliwia wybór rozporządzenia, które ma być używane podczas oceniania limitów zapasów. |
    | Przewóz drogowy towaru | Produkt z grupy CMR | CMR oznacza „substancje rakotwórcze, mutagenne i reprotoksyczne”. Ustawienie tej opcji na wartość **Tak** powoduje skonfigurowanie systemu do drukowania określonych ostrzeżeń i komunikatów związanych z obsługą tych substancji. |
    | Przewóz drogowy towaru | Opis grupowy materiału niebezpiecznego | Służy do wprowadzania tekstu określonych ostrzeżeń związanych z CMR i przewozem towarów drogą lądową. Tekst ten będzie zawarty w raporcie. |
    | Deklaracja spedytorów | Ostrzeżenie | Wprowadź tekst komunikatu ostrzegawczego, który ma być drukowany na formularzu deklaracji spedytora (na przykład „Ostrzeżenie: niebezpieczne towary, łatwopalne”). |
    | Deklaracja spedytorów | Deklaracja ze stopki | Umożliwia wprowadzenie tekstu komunikatu, który powinien być drukowany u dołu dokumentu deklaracji wysyłki. |
    | Język raportu dotyczącego towarów niebezpiecznych | Język raportu przewozu krajowego towarów niebezpiecznych | Umożliwia wybór domyślnego języka dla raportów materiałów niebezpiecznych skojarzonych z wysyłkami krajowymi. |
    | Język raportu dotyczącego towarów niebezpiecznych | Język raportu eksportu towarów niebezpiecznych | Umożliwia wybór domyślnego języka dla raportów materiałów niebezpiecznych skojarzonych z wysyłkami międzynarodowymi. |

## <a name="hazardous-materials-report"></a>Raport dot. materiałów niebezpiecznych

Raport dot. **materiałów niebezpiecznych** wyświetla listę wszystkich skonfigurowanych towarów i zdefiniowanych jako zawierające informacje o towarach niebezpiecznych. Tego raportu można używać do monitorowania i przeglądania informacji, które należy zachować. Strona raportu zawiera ograniczony wybór pól z konfiguracji materiałów niebezpiecznych. Można jednak dokonać personalizacji, aby dodać dodatkowe pola.

Aby wyświetlić ten raport, przejdź do **Zarządzania informacjami o produktach \> Zapytania i raporty \> Dokumentacja przewozowa materiałów niebezpiecznych \> Materiały niebezpieczne**.

## <a name="hazardous-material-stock-limit-report"></a><a name="stock-limit-report"></a>Raport dot. limitów zapasów materiałów niebezpiecznych

Raport o **Limicie zapasów materiałów niebezpiecznych** umożliwia monitorowanie poziomów zapasów niebezpiecznych materiałów w lokalizacjach magazynowych w celu upewnienia się, że pozostaną one w ramach wyznaczonych limitów bezpieczeństwa. Te limity pochodzą z limitów zdefiniowanych dla każdego zwolnionego produktu.

Aby wyświetlić ten raport, przejdź do **Zarządzania informacjami o produktach \> Zapytania i raporty \> Dokumentacja przewozowa materiałów niebezpiecznych \> Materiały niebezpieczne — limity zapasów**.

Więcej informacji na temat ustawiania limitów magazynowych dla zwolnionego produktu znajduje się w temacie [ustawienia limitów magazynowych dla produktów niebezpiecznych](hazmat-items.md#stock-limits).

Rozporządzenie używane do obliczania limitów zapasów jest zdefiniowane na stronie **Parametry zarządzania magazynem**. Przejdź do **Ustawień zarządzania magazynem \> Konfiguracji \> Parametrów zarządzania magazynem**, a następnie na karcie **Raporty** w polu **Limit zapasów materiałów niebezpiecznych** należy określić kod rozporządzenia. Aby uzyskać więcej informacji, zobacz sekcję [Konfigurowanie grupy sekwencji jednostek](#set-up) we wcześniejszej części tego artykułu.

## <a name="verified-gross-mass-report"></a>Zweryfikowany raport dotyczący masy brutto

**Zweryfikowany raport dot. masy brutto** umożliwia drukowanie informacji na temat wagi wysyłki.

Aby wygenerować i wydrukować ten raport, należy przejść do modułu **Zarządzanie magazynem \> Przesyłki \> Wszystkie wysyłki** i otworzyć odpowiednią wysyłkę. Następnie w okienku akcji w zakładce **Przesyłki** w grupie **Dokumenty dot. materiałów niebezpiecznych** należy wybrać opcję **Zweryfikowana masa brutto**.

## <a name="multimodal-dangerous-goods-report"></a>Towary niebezpieczne z wieloma metodami — raport

**Raport dot. towarów niebezpiecznych z wieloma metodami** jest dostarczany dla wysyłek, które muszą być transportowane za pomocą kombinacji metod transportu. Zazwyczaj jest ono używane, gdy wysyłka jest przenoszona najpierw lądowo i później drogą morską.

Aby wygenerować i wydrukować ten raport, należy przejść do modułu **Zarządzanie magazynem \> Przesyłki \> Wszystkie wysyłki** i otworzyć odpowiednią wysyłkę. Następnie w okienku akcji w zakładce **Przesyłki** w grupie **Dokumenty dot. materiałów niebezpiecznych** należy wybrać opcję **Towary niebezpieczne z wieloma metodami**.

Podczas generowania tego raportu informacje są zapisywane w taki sposób, aby można było je edytować i/lub ponownie wydrukować raport w razie konieczności. Aby edytować wygenerowany raport, przejdź do **Zarządzania magazynem \> Zapytania i raporty \> Dokumentacja dot. wysyłki materiałów niebezpiecznych \> Towary niebezpieczne z wieloma metodami** i znajdź odpowiedni raport na liście. Po zakończeniu edycji zawartości w razie konieczności wybierz opcję **Drukuj** w okienku akcji, aby wydrukować raport.

## <a name="shippers-declaration-report"></a>Deklaracja spedytorów — raport

Raport pt. **Deklaracja spedytorów** umożliwia drukowanie informacji związanych z deklaracją materiałów uwzględnionych w wysyłce.

Aby wygenerować i wydrukować ten raport, należy przejść do modułu **Zarządzanie magazynem \> Przesyłki \> Wszystkie wysyłki** i otworzyć odpowiednią wysyłkę. Następnie w okienku akcji w zakładce **Przesyłki** w grupie **Dokumenty dot. materiałów niebezpiecznych** należy wybrać opcję **Deklaracja spedytorów**.

## <a name="carriage-of-merchandise-by-road-report"></a>Przewóz drogowy towaru — raport

Raport pt. **Przewóz towarów drogą drogową** jest zbliżony do listu przewozowego, ale jest zwykle używany do transportu drogowego w Europie na mocy umowy dotyczącej międzynarodowych przepisów dotyczących międzynarodowego przewozu drogowego towarów niebezpiecznych (ADR). Ten raport korzysta z tekstu wydrukowanego dla danego towaru, chyba że zostanie ustawione pole **Opis grupy materiałów niebezpiecznych** na stronie **Parametry zarządzania magazynem**.

Aby wygenerować i wydrukować ten raport, należy przejść do modułu **Zarządzanie magazynem \> Przesyłki \> Wszystkie wysyłki** i otworzyć odpowiednią wysyłkę. Następnie w okienku akcji w zakładce **Przesyłki** w grupie **Dokumenty dot. materiałów niebezpiecznych** należy wybrać opcję **Przewóz towarów drogą lądową**.

Podczas generowania tego raportu informacje są zapisywane w taki sposób, aby można było je edytować i/lub ponownie wydrukować raport w razie konieczności. Aby edytować wygenerowany raport, przejdź do **Zarządzania magazynem \> Zapytania i raporty \> Dokumentacja dot. wysyłki materiałów niebezpiecznych \> Przewóz towarów drogą lądową** i znajdź odpowiedni raport na liście. Po zakończeniu edycji zawartości w razie konieczności wybierz opcję **Drukuj** w okienku akcji, aby wydrukować raport.

## <a name="shipment-summary-report"></a>Raport podsumowania wysyłki

Raport pt. **Podsumowanie wysyłki** zawiera informacje podsumowane przez kategorię transportu powiązaną ze zwolnionymi towarami.

Aby wygenerować i wydrukować ten raport, należy przejść do modułu **Zarządzanie magazynem \> Przesyłki \> Wszystkie wysyłki** i otworzyć odpowiednią wysyłkę. Następnie w okienku akcji w zakładce **Przesyłki** w grupie **Dokumenty dot. materiałów niebezpiecznych** należy wybrać opcję **Podsumowanie wysyłki**.

## <a name="bill-of-lading-report"></a>raport listów przewozowych

Jeśli dla systemu jest włączona funkcja materiałów niebezpiecznych, **raport listów przewozowych** zawiera kolumnę pt. **Materiały niebezpieczne**, która wskazuje, czy ładunek zawiera materiały niebezpieczne. Ten raport jest dostępny na stronie **Wszystkie ładunki**.

## <a name="packing-list-report"></a>Raport list pakowania

Jeśli dla systemu jest włączona funkcja materiałów niebezpiecznych, listy te zawierają dodatkowe informacje związane z drukowanym tekstem dotyczącym wysyłki dla danego towaru. Ten raport jest dostępny na stronie **Wszystkie ładunki**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]