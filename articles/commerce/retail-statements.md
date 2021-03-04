---
title: Zestawienia sieci sprzedaży
description: W tym temacie opisano sposób tworzenia i księgowania zestawień.
author: ashishmsft
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 85183
ms.assetid: df9c62a2-6f13-4a08-bdca-07d041172c1b
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Retail July 2017 update
ms.openlocfilehash: 4409811d2ef60174a316db10307dc7af4697398c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415060"
---
# <a name="retail-statements"></a>Zestawienia handlu detalicznego

[!include [banner](includes/banner.md)]

W programie Dynamics 365 Commerce proces księgowania zestawień jest używany do wykazywania transakcji następujących w aplikacjach Cloud POS lub Modern POS (MPOS). Proces księgowania zestawień używa harmonogramu dystrybucji, aby pobierać zbiór transakcji z punktu sprzedaży do aplikacji klienckiej w centrali (HQ). Parametry definiowane na stronach **Parametry handlu** i **Sklepy** są używane do wybierania transakcji pobieranych do poszczególnych zestawień.

Poniższa ilustracja przedstawia proces księgowania zestawień: W tym procesie transakcje rejestrowane w punkcie sprzedaży są przesyłane do klienta za pomocą harmonogramu Commerce. Gdy klient otrzyma transakcje, użytkownik może tworzyć, obliczać i księgować zestawienia transakcji dla sklepu.

[![Proces księgowania zestawień](./media/retail-statements.png)](./media/retail-statements.png)

## <a name="creating-and-posting-statements"></a>Tworzenie i księgowanie zestawień

Zestawienie można utworzyć ręcznie lub za pomocą procesów wsadowych, skonfigurowanych do uruchamiania okresowo przez cały dzień. W obu przypadkach poniższe kroki umożliwiają tworzenie i księgowanie zestawień.

### <a name="create-the-statement"></a>Tworzenie zestawienia

W tym kroku identyfikuje się sklep, dla którego ręcznie utworzono zestawienie. Po skonfigurowaniu procesu wsadowego można automatycznie utworzyć zestawienia dla wszystkich sklepów, zgodnie z harmonogramem, który zdefiniujesz.

### <a name="calculate-the-statement"></a>Oblicz zestawienie

W tym kroku wiersze transakcji są wybierane na podstawie kryteriów, które są zdefiniowane dla każdego sklepu na stronach **Parametry handlu** i **Sklepy**. Na tych stronach można zdefiniować kryteria i określić sposób obliczania transakcji. Aby wyświetlić listę transakcji uwzględnionych w zestawieniu przed rozpoczęciem obliczania, użyj strony **Transakcje**.

Obliczenie zestawienia wykorzystuje deklaracje środków płatniczych z kas jako kwotę obliczoną. Można również ręcznie wprowadzić kwotę obliczoną. Zestawienie pokazuje różnicę między kwotą wynikającą z transakcji sprzedaży a faktycznie obliczoną kwotą zsumowaną dla wszystkich metod płatności. Zestawienie zostanie zaksięgowane tylko pod warunkiem, że kwota rozbieżności nie przekroczy maksymalnej dozwolonej rozbieżności dla księgowania, określonej dla sklepu.

> [!NOTE]
> Proces obliczania zestawienia używa globalnej sekwencji numerów.

Podczas obliczania zestawienia, obliczenie obejmuje następujące zadania:

- Dla wybranego zakresu dat oznaczanie transakcji, które nie zostały uwzględnione w obliczaniu poprzedniego zestawienia.
- Obliczanie sum, które zostały wpłacone w ramach wybranych transakcji. Wyniki są pokazywane w wierszach zestawienia, w zależności od metody zestawienia:

    - Jeśli dla metody zestawienia wybrano **Suma**, dla każdej metody płatności w wybranych transakcjach tworzony jest odpowiedni wiersz.
    - Jeśli dla metody zestawienia wybrano **Pracownicy**, dla każdej metody płatności w transakcjach wykonanych przez określonego pracownika, tworzony jest odpowiedni wiersz.
    - Jeśli dla metody zestawienia wybrano **Terminal w punkcie sprzedaży**, dla każdej metody płatności w transakcjach wykonanych przez na wybranym rejestrze, tworzony jest odpowiedni wiersz.
    - Jeśli dla metody zestawienia wybrano **Zmiana**, dla każdej metody płatności w transakcjach wykonanych podczas zmiany tworzony jest odpowiedni wiersz.

Jeśli zaznaczono pole wyboru **Podziel wg metody zestawienia** na stronie **Sklepy**, oddzielne zestawienie jest tworzone na podstawie wartości wybranej w polu **Metoda zestawienia**.

Jeśli godziny pracy sklepu kończą się po północy, można skonfigurować księgowanie zestawienia na koniec dnia roboczego, a nie na koniec dnia kalendarzowego.

Na stronie **Sklepy** na skróconej karcie **Zestawienie/zamknięcie** w polu **Koniec dnia roboczego** wprowadź czas rejestracji ostatniej transakcji w celu jej uwzględnienia w zestawieniu dla danego dnia. Zaznacz pole wyboru **Księguj z dniem roboczym**, aby zaksięgować transakcje w tym samym dniu roboczym. Podczas księgowania zestawienia transakcje, które są rejestrowane w tym samym dniu roboczym, mogą być zawarte w tym samym zamówieniu sprzedaży, nawet jeśli niektóre transakcje następują przed północą, a inne transakcje następują po północy.

#### <a name="example-post-a-statement-for-a-business-day-that-extends-over-two-calendar-days"></a>Przykład: Księgowanie zestawienia dla dnia roboczego, który rozciąga się na dwa dni kalendarzowe

Sklep jest otwarty między 8:00 a 3:00, a w konfiguracji sklepu zaznaczono pole wyboru **Księguj z dniem roboczym**. 31 maja sklep rejestruje transakcje między 8:00 a północą. Sklep rejestruje także transakcji między 00:01 a 3:00 w dniu 1 czerwca.

Po zaksięgowaniu zestawienia dla sklepu po zakończeniu dnia roboczego generowane jest zamówienie sprzedaży zawierające wszystkie transakcje, które zostały zarejestrowane w godzinach otwarcia pomiędzy 8:00 a 3:00, nawet jeśli transakcje miały miejsce w dwóch dniach — 31 maja i 1 czerwca.

Jeśli dla tego samego sklepu pole wyboru **Księguj z dniem roboczym** jest wyczyszczone, oddzielne zamówienia sprzedaży są generowane, gdy sklep księguje zestawienie pod koniec dnia roboczego. Jedno zamówienie sprzedaży zawiera transakcje, które zostały zarejestrowane między godzinami 8:00 a północą 31 maja, a drugie zamówienie sprzedaży zawiera transakcje, które zostały zarejestrowane między godzinami roboczymi 00:01 AM a 3:00 w dniu 1 czerwca.

> [!NOTE]
> Przed utworzeniem zestawień, należy zamknąć zmiany w ustalonym okresie.

### <a name="post-the-statement"></a>Księgowanie zestawienia

Podczas księgowania zestawienia, dla sprzedaży detalicznej w sprawozdaniu tworzone są zamówienia sprzedaży i faktury.

- Sprzedaże dla transakcji kasowych i transakcji przeniesienia są agregowane do jednego zamówienia sprzedaży i zafakturowane dla domyślnego odbiorcy, który jest przypisany do sklepu.
- Sprzedaż, dla której dodano odbiorcę w transakcji w programie POS, generuje oddzielne zamówienia sprzedaży i faktury, po jednej dla każdego unikatowego odbiorcy.

Arkusze płatności są automatycznie tworzone dla płatności w zestawieniu, a zapasy są aktualizowane dla sklepu z punktem sprzedaży.


[!INCLUDE[footer-include](../includes/footer-banner.md)]