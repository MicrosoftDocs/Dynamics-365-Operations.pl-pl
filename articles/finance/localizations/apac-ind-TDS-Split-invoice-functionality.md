---
title: Funkcje dzielenia faktury
description: W tym temacie opisano ustawienia i funkcje dzielenia faktur według adresu dostawy i numeru konta podatkowego (TAN).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 8906461f151f80c22d41fa91a46d761d2a5cf2fff50560cc0d388d279c5bdc7d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742184"
---
# <a name="split-invoice-functionality"></a>Funkcje dzielenia faktury

[!include [banner](../includes/banner.md)]

W tym temacie opisano ustawienia i funkcje dzielenia faktur według adresu dostawy i numeru konta podatkowego (TAN).

Na stronie **Parametry rozrachunków z dostawcami**, na karcie **Ogólne** zaznacz pole wyboru **Przyjęcie produktu** lub **Faktura**, aby zakwitować i podzielić przyjęcie produktu lub fakturę, która ma różne adresy dostawy i numer TAN na stronie **Zamówienie zakupu**. Zaksięgowana faktura zostanie następnie podzielona według adresu dostawy i TAN.

Na karcie **Aktualizacja zbiorcza**, w wierszu **Informacje o dostawie**, w wierszu **Informacji o dostawie**, ustaw opcję **Potwierdzenie**, **Lista pobrania**, **Dokument dostawy** lub **Faktura** na **Tak**, aby zakturować i podzielić potwierdzenie, listę pobrania, dokument dostawy lub fakturę, dla których na stronie **zamówienia sprzedaży** są zdefiniowane różne adresy dostawy i TAN. Faktura zostanie podzielona najpierw według adresu dostawy, a następnie według numeru TAN.

> [!IMPORTANT]
> - Jeśli w ustawieniach **informacji o dostawie** nie zostanie ustawiona wartość **Tak**, faktura zostanie zaksięgowana jako jedna faktura. Nie nastąpi podział faktury.
> - Aby podzielić i zakturować dokument dostawy, w którym wiersze faktury mają różne adresy dostawy i numer TAN, w opcji **Dokument dostawy** dla **informacji o dostawie** musi być ustawiona wartość **Tak**.
> - Aby podzielić i zakturować fakturę, w którym wiersze faktury mają różne adresy dostawy i numer TAN, w opcji **Faktura** dla **informacji o dostawie** musi być ustawiona wartość **Tak**.
> - Aby zaksięgować fakturę, w której wiersze faktury mają różne adresy dostawy, ale ten sam numer TAN, w opcji **Faktura** dla **informacji o dostawie** musi być ustawiona wartość **Nie**. Faktura zostanie podzielona najpierw według adresu dostawy.

## <a name="example"></a>Przykład

W tym przykładzie opcja **Faktura** dla **informacji o dostawie** ma wartość **Tak** na karcie **Aktualizacja zbiorcza** na stronie **Parametry rozrachunków z dostawcami**. Księgowana jest faktura zakupu, która zawiera następujące ustawienia adresów dostawy i numerów TAN w wierszach:

- **Wiersz pozycji 1:** adres dostawy 1, TAN-ABCD12345A
- **Wiersz pozycji 2:** adres dostawy 1, TAN-ABCD12345A
- **Wiersz pozycji 3:** adres dostawy 2, TAN-ABCE12345B
- **Wiersz pozycji 4:** adres dostawy 3, TAN-ABCD12345A

W takim przypadku oryginalna faktura jest dzielona na dwie faktury i księgowana w następujący sposób:

- Faktura 1 jest księgowana dla pozycji 1 i 2 pozycji, ponieważ oba wiersze mają ten sam adres dostawy i numer TAN.
- Faktura 2 jest księgowana dla wiersza 3.
- Faktura 3 jest księgowana dla wiersza 4.
