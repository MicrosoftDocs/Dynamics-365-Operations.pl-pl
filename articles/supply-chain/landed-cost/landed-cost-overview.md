---
title: Moduł Kosztów z wyładunkiem
description: Moduł kosztów z wyładunkiem pomaga firmom usprawnić operacje wysyłki przychodzącej, dając użytkownikom pełną kontrolę finansową i logistyczną nad importowanym ładunkiem, od producenta po magazyn.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: intro-internal
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: e646b5fed29aa4c6e67a83703a51c4a322a1918b
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2021
ms.locfileid: "6338430"
---
# <a name="landed-cost-module"></a>Moduł Kosztów z wyładunkiem

[!include [banner](../../includes/banner.md)]

Moduł **kosztów z wyładunkiem** pomaga firmom usprawnić operacje wysyłki przychodzącej, dając użytkownikom pełną kontrolę finansową i logistyczną nad importowanym ładunkiem, od producenta po magazyn. W przypadku towarów importowanych koszty z wyładunkiem mogą uwzględniać co najmniej 40 procent łącznego kosztu każdego importowanego towaru. W związku z tym zadaniem jest dokładne oszacowanie kosztów z wyładunkiem.

Firmy mogą używać funkcji Koszt z wyładunkiem w celu wykonania następujących zadań:

- Szacowanie kosztów z wyładunkiem w czasie tworzenia podróży.
- Koszty z wyładunkiem ładunku wielu towarów i zamówień zakupu lub zamówień przeniesienia w ramach jednej podróży.
- Obsługuje przenoszenie towarów między lokalizacjami fizycznymi, rozpoznając koszty z wyładunkiem.
- Rozpoznaj naliczenia dla przewożonych towarów.

Koszt z wyładunkiem zapewnia dokładne i terminowe szacowanie kosztów z wyładunkiem narzutów. Jednocześnie zapewnia zwiększony wgląd finansowy i logistyczny w rozszerzony łańcuch dostaw. Pomaga także redukować procesy administracyjne wyceny i błędy wyceny.

## <a name="highlights"></a>Najważniejsze punkty

### <a name="voyages"></a>Podróże

W kosztach wyładunku podróż jest odrębnym przemieszczeniem z lokalizacji wyjściowej przez określony zestaw miejsc docelowych w określonym czasie do określonej lokalizacji magazynu przychodzącego. Zamówienia zakupu i wiersze zamówienia można dodać do pojedynczego kontenera lub wielu kontenerów na rejs, a koszty zostaną prawidłowo przypisane do pozycji towaru. Zamówienia i wiersze zamówień można dodawać w różnych firmach w celu pojedynczych podróży.

### <a name="item-ownership"></a>Prawa własności do pozycji

W Microsoft Dynamics 365 Supply Chain Management towary są zwykle odbierane w miejscu docelowym magazynu, a następnie fakturowane. Jednak zgodnie z większością międzynarodowych umów handlowych firma przejmuje własność towarów od momentu opuszczenia ich pierwotnego portu, zanim zostały one fizycznie odebrane. Koszt z wyładunkiem umożliwia firmom fakturowanie towarów przed ich fizycznym otrzymaniem. To pojęcie jest nazywane towarami w drodze. Tworzy nowy typ zamówienia w celu zarządzania przyjęciem towarów po zafakturowaniu oryginalnego zamówienia zakupu.

### <a name="costs"></a>Koszty

W przypadku tworzenia podróży w kosztach z wyładunkiem koszty mogą zostać do niego automatycznie dodane. Koszty te są ustawiane w koszcie z wyładunkiem i dostępne są dla nich różne opcje kosztowe i podstawy kosztowe. Każdy koszt można ustawić dla różnych poziomów podróży i przypisać do poziomu towaru za pomocą reguł podziału, które obsługują ilość, objętość, wagę, kwotę i zdefiniowane dzielniki objętości. Te szacowane koszty zapewniają dokładne oszacowanie wszystkich kosztów podróży.

Koszt wyładunku obejmuje następnie wstępne księgowanie / naliczanie szacunkowych kosztów wyładunku w celu zapewnienia dokładnego obliczenia szacunkowych kosztów w momencie tworzenia rejsu. Ponieważ te automatyczne koszty są fakturowane, szacowane koszty są odwracane i zastępowane kosztami rzeczywistymi na podstawie faktur kosztowych.

Koszty rzeczywiste to odwrócone szacowane koszty, które są księgowane w momencie fakturowania kosztów przy użyciu kont rozliczeniowych, które są skonfigurowane dla każdego typu kosztu (na przykład cło, fracht i ubezpieczenie). Te wpisy są zgodne z zachowaniem związanym z publikowaniem, które jest skojarzone z określonym elementem. Automatycznie aktualizują księgowanie zapasów, niezależnie od tego, czy typ księgowania to pierwsze na wejściu, pierwsze na wyjściu (FIFO), ostatnie na wejściu, pierwsze na wyjściu (LIFO), ruchomą średnią ważoną czy ruchomą średnią. Wszystkie typy księgowania grup modeli magazynu są obsługiwane. W przypadku księgowania średniej ruchomej i kosztów standardowych dostępne są konta odchyleń ceny zakupu, które umożliwiają księgowanie różnic między kosztami szacunkowymi a kosztami rzeczywistymi.

### <a name="item-and-order-tracking"></a>Śledzenie towarów i zamówień

Gdy podróż przenosi się z lokalizacji docelowej do końcowego magazynu docelowego, użytkownicy mogą zaktualizować każdy wymagany *etap* lub etap podróży. Dla każdego etapu określany jest czas realizacji i status wysyłki. Identyfikowane są również potwierdzone daty dostawy dla przejścia do następnego etapu podróży. Razem te daty dostawy zapewniają szacowaną datę dostawy towarów do magazynu przychodzącego. Użytkownicy mogą zmienić te daty dostawy. W takim przypadku szacowana data dostawy towarów jest automatycznie aktualizowana na podstawie czasów realizacji i podróży. Widoczność towarów w drodze według podróży i statku jest dostępna dla kontenerów przed odebraniem towarów. Ponieważ daty są aktualizowane w każdym wierszu zamówienia zakupu, firmy mają większą kontrolę nad logistyką i planowaniem magazynu.

## <a name="landed-cost-concepts"></a>Koncepcje kosztów z wyładunkiem

W poniższej tabeli przedstawiono podstawowe pojęcia dotyczące kosztu z wyładunkiem.

| Koncepcja | opis |
|---|---|
| Podróż | Zazwyczaj podróż to jeden statek. Jednak, w zależności od stosowanej przez użytkownika procedury, może to być jeden dostawca lub jedno zamówienie zakupu. Używanie tego pojęcia nie ma żadnych ograniczeń. |
| Folio | Folio jest często określone przez przepisy celne. Może ono składać się z jednego towaru dostawcy dla jednej jednostki/firmy na wysyłkę. Towary w folio mogą znajdować się w jednym kontenerze lub rozłożone na wiele kontenerów. |
| Kontener wysyłkowy | Wiersze zamówienia zakupu są zawarte w kontenerach wysyłkowych. Znajdują się one na poziomie poniżej poziomu wysyłki. Są one zwykle używane, jeśli koszty są rozdzielane na towary według kontenerów lub jeśli odbiór odbywa się na kontener. |
| Typ kontenera wysyłkowego | Typy kontenerów wysyłkowych mogą określać cenę typu kosztu (na przykład fracht). Zawierają one również przydatne informacje o wysyłce. |
| Typ kosztu | Typy kosztów identyfikują koszty związane z importem, takie jak cło, fracht lub ubezpieczenie. |
| Koszt automatyczny | Automatyczne koszty działają jak umowy handlowe. Koszt automatyczny jest połączony z poziomem podróży. |
| Port | Porty to obszary, z których są odbierane i przenoszone towary. |
| Statek | Statek to nośnik używany do transportu towarów, takich jak statek lub samolot. |
| Towar w drodze | W zależności od ustawień towary są wkładane do magazynu w drodze po zaktualizowaniu faktury. |
| Działanie | Działania mogą służyć do przechowywania każdego znaczącego etapu podróży między dwoma portami. Można ich używać do aktualizowania dat. |
| Szablon podróży | Szablony podróży to trasy, które przejmą towary między dwoma portami. |

Aby uzyskać porównanie terminologii i funkcji modułów **Koszty z wyładunkiem** i **Zarządzanie transportem** (TMS), zobacz temat [Koszty z wyładunkiem a zarządzanie transportem](landed-cost-vs-tms.md).
