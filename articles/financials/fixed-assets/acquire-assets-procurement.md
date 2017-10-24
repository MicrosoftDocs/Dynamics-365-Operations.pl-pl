---
title: "Nabywania środków trwałych za pomocą zaopatrzenia"
description: "W tym artykule opisano, jak skonfigurować integrację między modułami Środki trwałe i Rozrachunki z dostawcami, aby automatycznie były tworzone środki trwałe na podstawie zamówień zakupu lub faktur od dostawców albo automatycznie były księgowane transakcje nabycia i korekty wartości początkowej dla środków trwałych."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3481
ms.assetid: d4e73a3f-633b-48b2-b8db-7a4a59a4d7ec
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 84e7e6eb17e5741a2984c570786a495864ffbc74
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="acquire-assets-through-procurement"></a>Nabywania środków trwałych za pomocą zaopatrzenia

[!include[banner](../includes/banner.md)]


W tym artykule opisano, jak skonfigurować integrację między modułami Środki trwałe i Rozrachunki z dostawcami, aby automatycznie były tworzone środki trwałe na podstawie zamówień zakupu lub faktur od dostawców albo automatycznie były księgowane transakcje nabycia i korekty wartości początkowej dla środków trwałych.

 Poniżej przedstawiono metody do integracji Środków trwałych i Rozrachunków z dostawcami. W odniesieniu do wszystkich środków trwałych trzeba użyć tej samej metody:
-   Środek trwały jest tworzony ręcznie zanim numer środka trwałego zostanie dodany do wiersza zamówienia zakupu lub faktury od dostawcy. Dla tego środka jest automatycznie księgowana transakcja nabycia po zaksięgowaniu faktury od dostawcy. To jest metoda domyślna.
-   Środek trwały jest tworzony ręcznie zanim numer środka trwałego zostanie dodany do wiersza zamówienia zakupu lub faktury od dostawcy. Dla tego środka nie jest księgowana transakcja nabycia po zaksięgowaniu faktury od dostawcy.
-   Środek trwały jest tworzony automatycznie podczas księgowania dokumentu przyjęcia produktów lub faktury od dostawcy, jeśli zaznaczono pole wyboru Utwórz nowy środek trwały. Dla tego środka jest automatycznie księgowana transakcja nabycia po zaksięgowaniu faktury od dostawcy.
-   Środek trwały jest tworzony automatycznie podczas księgowania dokumentu przyjęcia produktów lub faktury od dostawcy, jeśli zaznaczono pole wyboru Utwórz nowy środek trwały. Dla tego środka nie jest księgowana transakcja nabycia po zaksięgowaniu faktury od dostawcy.

Wybierz jedną z dwóch pierwszych metod, jeśli preferujesz ręczne tworzenie środków trwałych, a następnie przypisz numer środka trwałego do zamówienia zakupu lub faktury od dostawcy. Wybierz jedną z dwóch ostatnich metod, jeśli preferujesz bardziej elastyczne podejście: czasami możesz tworzyć środki trwałe ręcznie, a czasami możesz automatycznie tworzyć nowy środek trwały na podstawie informacji o środku trwałym zawartych w wierszu szczegółów dotyczących towaru. 

Niezależnie od tego, czy środki trwałe są tworzone ręcznie, czy stosowane jest bardziej elastyczne podejście, druga decyzja, jaką trzeba podjąć, dotyczy tego, czy transakcja nabycia może zostać zaksięgowana tylko w module Środki trwałe, czy w momencie zaksięgowania faktury od dostawcy. Niektóre organizacje wolą, aby użytkownicy ręcznie tworzyli nabycia i transakcje nabycia w module Środki trwałe za pomocą ręcznych wpisów w arkuszu lub propozycji. 

W tym temacie szczegółowo omówiono każdą z metod.

## <a name="methods-for-manually-creating-fixed-assets"></a> Metody, w których środek trwały jest tworzony ręcznie
W momencie zaksięgowania faktury od dostawcy, której wiersze zawierają numer środka trwałego, jeśli została zaznaczona opcja Zezwalaj na nabywanie środków trwałych z zakupów na stronie Parametry środków trwałych, nabycie jest księgowane automatycznie i stan środka trwałego zmienia się na Otwarty. 

Jeśli nabycie nie może zostać zaksięgowane, można ręcznie wprowadzić transakcję nabycia w module Środki trwałe lub użyć propozycji nabycia w arkuszu Środki trwałe w celu utworzenia wielu transakcji nabycia naraz.

> [!NOTE]                                                                                                                              
> Jeśli moduł Środki trwałe jest tak skonfigurowany, że księgowanie transakcji nabycia jest ograniczone do określonej grupy użytkowników, użytkownik musi być członkiem tej grupy, aby mógł księgować transakcje nabycia na podstawie faktur.

## <a name="methods-for-automatically-creating-fixed-assets"></a> Metody, w których środek trwały jest tworzony automatycznie
Podczas księgowania dokumentu przyjęcia produktów, w którego wierszu zaznaczono opcję Utwórz nowy środek trwały, zostanie utworzony nowy środek trwały o stanie Jeszcze nie nabyty. Następnie w momencie zaksięgowania faktury od dostawcy z tym nowym środkiem trwałym zostaje zaksięgowana transakcja nabycia dla nowego środka trwałego i stan środka trwałego zmienia się na Otwarty, o ile moduł Środek trwały jest tak skonfigurowany, że zezwala na nabycia środków trwałych z modułu Rozrachunki z dostawcami, i użytkownik jest członkiem grupy użytkowników mającej prawo księgować transakcje nabycia. 

Jeśli pole wyboru Nowy środek trwały? nie było zaznaczone w wierszu zakupu w momencie księgowania dokumentu przyjęcia produktu, ale jest zaznaczone w momencie księgowania faktury od dostawcy, tworzony i nabywany jest nowy środek trwały o stanie Otwarty, o ile moduł Środki trwałe główna jest tak skonfigurowany, że zezwala na tworzenie i nabywanie środków trwałych. W momencie zaksięgowania faktury od dostawcy nie jest tworzony dodatkowy środek trwały, jeśli został on już utworzony w momencie zaksięgowania dokumentu przyjęcia produktów.

### <a name="capitalization-threshold"></a>Próg kapitalizacji

W przypadku używania metody, w której środek trwały jest tworzony i nabywany automatycznie, system można tak skonfigurować, aby sprawdzał, czy kwota zakupu środka trwałego nie jest niższa niż określony próg kapitalizacji dla amortyzacji środka trwałego. Jeśli nie, podczas tworzenia środka trwałego w module Rozrachunki z dostawcami zostanie dla niego zaznaczona opcja Amortyzacja. 

Próg kapitalizacji to kwota w walucie, która określa, czy środki trwałe podlegają amortyzacji. Jeśli na przykład zostanie nabyty środek trwały i kwota nabycia jest niższa niż próg kapitalizacji, środek trwały nie podlega amortyzacji; jeśli kwota nabycia jest równa progowi kapitalizacji lub od niego wyższa, środek trwały podlega amortyzacji. 

Próg kapitalizacji można skonfigurować na stronie Grupy środków trwałych.

## <a name="scenario"></a>Scenariusz
W poniższym scenariuszu przedstawiono pełny cykl integracji między modułami Środki trwałe i Rozrachunki z dostawcami. Pokazano również przykładową konfigurację i opisano użycie propozycji nabycia. 

W tym scenariuszu system jest skonfigurowany następująco:

-   Środki trwałe są tworzone automatycznie podczas księgowania dokumentu przyjęcia produktów lub faktury od dostawcy, ale moduł Środki trwałe jest tak skonfigurowany, że uniemożliwia księgowanie transakcji nabycia w module Rozrachunki z dostawcami.
-   Konta są określone w polu Typ konta dla pozycji Przychód środków trwałych i Rozchód środków trwałych na stronie Grupy pozycji.
-   Próg kapitalizacji dla grupy Komputery (COMP) wynosi 1500.
-   Zadanie użytkownika polega na wprowadzeniu zamówienia zakupu dla nowego komputera przenośnego, którego będzie używał jeden z pracowników, zaksięgowaniu tego zamówienia zakupu, sprawdzeniu, czy pracownik ds. spedycji zaksięgował dokument przyjęcia produktów, zaksięgowaniu faktury od dostawcy, a następnie sprawdzeniu, czy księgowy zaktualizował stan środka trwałego „komputer przenośny” do Otwarty.

Najpierw użytkownik używa strony Zamówienie zakupu w celu wprowadzenia szczegółów dotyczących komputera przenośnego, który kosztuje 1600 zł. Użytkownik zaznacza opcję Nowy środek trwały? na skróconej karcie Środki trwałe w wierszach zamówienia zakupu, wybiera COMP jako grupę środków trwałych i zapisuje zamówienie zakupu. 

Po odebraniu komputera przenośnego pracownik ds. spedycji wprowadza i księguje dokument przyjęcia produktów w celu zarejestrowania odebrania komputera przenośnego. Zostaje utworzony środek trwały „komputer przenośny” o stanie Jeszcze nie nabyty. Kwota przekracza próg kapitalizacji. Z tego względu zaznaczono opcję Amortyzacja w księgach dla środka trwałego „komputer przenośny”. Nastąpiły poniższe transakcje.

| Opis                               | Konto             | Debet    | Kredyt   |
|-------------------------------------------|---------------------|----------|----------|
| Zakup, dokument przyjęcia produktów — zakup        | Przychody niezafakturowane | 1600,00 |          |
| Zakup, dokument przyjęcia produktów — konto przeciwstawne zakupu | Naliczone zakupy   |          | 1600,00 |

Następnie użytkownik księguje fakturę od dostawcy dla komputera przenośnego. Stan komputera przenośnego nie zmienia się, ponieważ moduł Środki trwałe jest tak skonfigurowany, że uniemożliwia zaksięgowanie transakcji nabycia w momencie zaksięgowania faktury od dostawcy. W monecie księgowania faktury od dostawcy była zaznaczona opcja Utwórz nowy środek trwały. Dlatego zostało użyte konto przychodu środka trwałego. Konto Rozchód środków trwałych nie zostało użyte, ponieważ nabycie nie zostało zaksięgowane; zostanie ono użyte później, gdy księgowy organizacji zaksięguje transakcję nabycia w module Środki trwałe za pomocą propozycji nabycia. 

Nastąpiły poniższe transakcje.

| Opis                               | Konto             | Debet    | Kredyt   |
|-------------------------------------------|---------------------|----------|----------|
| Zakup, dokument przyjęcia produktów — konto przeciwstawne zakupu | Naliczone zakupy   | 1600,00 |          |
| Saldo dostawcy                            | Rozrachunki z dostawcami    |          | 3200,00 |
| Zakup, przychód środków trwałych             | Wydatek komputerowy    | 1600,00 |          |
| Zakup, dokument przyjęcia produktów — zakup        | Przychody niezafakturowane |          | 1600,00 |

Na koniec księgowy przegląda wszystkie środki trwałe, które mają stan Jeszcze nie nabyty. Sprawdzany jest nowy środek trwały „komputer przenośny”. Księgowy otwiera stronę Propozycja nabycia z wierszy arkusza środków trwałych, a następnie tworzy transakcje nabycia dla wszystkich środków trwałych, które mają fakturę, ale nadal znajdują się w stanie Jeszcze nie nabyto. Po zaksięgowaniu arkusza stan środka trwałego „komputer przenośny” został zmieniony na Otwarty. Zostaje zaksięgowana kwota uznania na koncie Rozchód środków trwałych oraz potrącenie na koncie nabycia środka. 

Oto różne odmiany tego scenariusza:

-   Gdyby moduł Środki trwałe był tak skonfigurowany, że zezwalałby na księgowanie transakcji nabycia środków trwałych w momencie księgowania faktur od dostawców, księgowy nie musiałby używać propozycji nabycia w module Środki trwałe, ponieważ zostałaby utworzona transakcja nabycia. Ponadto w momencie zaksięgowania faktury od dostawcy byłyby aktualizowane inne konta. Zamiast wydatku na komputer, zostaje obciążone konto zapasów przychodu środków trwałych i występują dwie dodatkowe transakcje: obciążenie konta nabycia środków trwałych i uznanie konta zapasów rozchodów środków trwałych.
-   Jeśli pole wyboru Utwórz nowy środek trwały nie jest zaznaczone podczas księgowania dokumentu przyjęcia produktów, nie jest w tym momencie tworzony środek trwały. Jeśli pole wyboru Utwórz nowy środek trwały zostanie zaznaczone przed zaksięgowaniem faktury od dostawcy, tworzony jest środek trwały o stanie Jeszcze nie nabyto lub Otwarty, o ile transakcje nabycia są księgowane w momencie księgowania faktur od dostawców.
-   Jeśli komputer przenośny kosztował 1400 zamiast 1600, nie zostanie osiągnięty próg kapitalizacji. Środek trwały zostanie utworzony, a zaznaczenie opcji Amortyzacja wyczyszczone.
-   Jeśli jest używany rejestr faktur, należy po zaksięgowaniu rejestru faktur użyć strony Arkusz zatwierdzania faktur w celu pobrania załącznika, połączyć zamówienie zakupu z fakturą od dostawcy, zaznaczyć opcję Utwórz nowy środek trwały, a następnie zaksięgować fakturę od dostawcy. Jeśli użytkownik jest członkiem grupy użytkowników, która może tworzyć transakcje nabycia, tworzone jest nabycie oraz środek trwały o stanie Otwarty.
-   W przypadku odebrania tylko częściowej ilości nie jest tworzone nabycie środka trwałego dla pierwszej faktury od dostawcy z powodu ograniczeń dotyczących grup użytkowników. Zaksięgowanie nabycia dla drugiej faktury od dostawcy, dotyczącej pozostałej zamówionej ilości, jest możliwe tylko wtedy, gdy transakcja nabycia została już wprowadzona dla pierwszej faktury od dostawcy i użytkownik jest członkiem grupy użytkowników mającej prawo księgować nabycia.


Aby uzyskać więcej informacji, zobacz [Integracja środków trwałych](fixed-asset-integration.md).




