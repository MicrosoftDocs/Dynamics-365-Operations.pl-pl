---
title: Faktury zaliczkowe w rozwiązaniu Commerce dla Europy Wschodniej
description: W tym artykule opisano, jak skonfigurować faktury zaliczkowe w aplikacji Commerce dla Europy Wschodniej.
author: epopov
ms.date: 10/23/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.search.industry: Retail
ms.author: epopov
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: c71f0ddb0a040202a486e63b4812ac4f84ad36aa
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883923"
---
# <a name="advance-invoices-for-commerce-for-eastern-europe"></a>Faktury zaliczkowe w rozwiązaniu Commerce dla Europy Wschodniej

[!include [banner](../includes/banner.md)]

Informacje zawarte w tym artykule mają zastosowanie do lokalizacji dla Europy Wschodniej i są specyficzne dla branży handlowej.

W Polsce, na Węgrzech i w Czechach po otrzymaniu od klienta przedpłaty za pośrednictwem aplikacji punktu sprzedaży (POS) przedpłatę należy zarejestrować do celów podatkowych, a także należy wygenerować i wydrukować dokument faktury zaliczkowej zawierający kwotę przedpłaty. Ponadto w Polsce transakcje faktur zaliczkowych muszą być księgowane w księdze głównej.

Gdy faktura za zamówienie sprzedaży jest finalnie księgowana, ostateczny dokument powinien uwzględniać dane faktury zaliczkowej z oznaczeniem wszelkich przedpłat.

Jeśli generujesz zamówienia sprzedaży z modułu Rozrachunki z odbiorcami, należy ręcznie wygenerować faktury zaliczkowe przy użyciu procedury opisanej w temacie [Faktury zaliczkowe dla Europy Wschodniej](/dynamics365/unified-operations/financials/localizations/emea-advance-invoice). Jeśli generujesz zamówienia sprzedaży z aplikacji POS, system automatycznie wygeneruje i zaksięguje faktury zaliczkowe.

## <a name="supported-scenarios"></a>Obsługiwane scenariusze

Obsługiwane są następujące scenariusze:

- Tworzenie i księgowanie faktury zaliczkowej.
- Modyfikowanie kwoty wpłaty. Jeżeli odbiorca postanowi zwiększyć kwotę wpłaty, zostanie wystawiona dodatkowa faktura zaliczkowa. W przypadku wszystkich innych zmian kwoty wpłaty (na przykład w przypadku modyfikacji zamówienia odbiorcy) zostanie utworzona faktura korygująca do wygenerowanej wcześniej faktury zaliczkowej, a następnie zostanie utworzona i zaksięgowana nowa faktura zaliczkowa na skorygowaną kwotę.
- Anulowanie zamówienia sprzedaży mającego połączone faktury zaliczkowe. W takim przypadku jest tworzona faktura korygująca do faktury zaliczkowej.
- Zaksięgowanie faktury za zamówienie sprzedaży mającej połączone faktury zaliczkowe. Faktura zaliczkowa połączona z zamówieniem sprzedaży jest stornowana na kwotę faktury sprzedaży. Transakcje faktur zaliczkowych są rozliczane za pomocą transakcji wycofania faktur zaliczkowych.

## <a name="set-up-advance-invoices"></a>Konfigurowanie faktur zaliczkowych

### <a name="turn-on-the-functionality-for-creating-advance-invoices"></a>Włączanie funkcjonalności tworzenia faktur zaliczkowych

1. Wybierz kolejno opcje **Commerce \> Ustawienia central \> Parametry \> Parametry Commerce**.
2. Na karcie **Zamówienia odbiorców** na skróconej karcie **Zamówienie** ustaw opcję **Utwórz fakturę zaliczkową dla wpłaty** na **Tak**.

### <a name="define-the-parameters-for-posting-advance-invoices"></a>Definiowanie parametrów księgowania faktur zaliczkowych

1. Wybierz kolejno pozycje **Rozrachunki z odbiorcami \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami**.
2. Na karcie **Aktualizacje** na skróconej karcie **Faktura zaliczkowa** ustaw wartości w polach **Profil księgowania**, **Grupa podatków** i **Grupa podatków dla pozycji**. Jeśli te pola są ustawione poprawnie, faktura zaliczkowa zostanie zaksięgowana. Jeśli te pola nie są ustawione, faktury zaliczkowe nie będą księgowane.

### <a name="turn-off-posting-of-the-sales-tax-on-prepayment-journal-voucher"></a>Wyłączanie księgowania podatku z załącznika arkusza zaliczki

Podatek figurujący w załączniku arkusza zaliczki nie może być księgowany, jeśli jest włączona funkcja księgowania faktur zaliczkowych. Aby sprawdzić, czy ten wymóg jest spełniony, wykonaj następujące kroki.

1. Wybierz kolejno pozycje **Rozrachunki z odbiorcami \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami**.
2. Na karcie **Księga i podatek** na skróconej karcie **Płatność** upewnij się, że następujące pola są puste lub zawierają wartość **Nie**:

    - Podatek w załączniku arkusza zaliczki
    - Profil księgowania z użyciem załącznika arkusza zaliczki
    - Grupa podatku zaliczki
    - Grupa podatków dla pozycji

## <a name="print-advance-invoices"></a>Drukowanie faktur zaliczkowych

Faktury zaliczkowe można drukować z aplikacji POS na drukarce systemu Microsoft Windows podłączonej do stacji sprzętowej. Dostępne są dwie opcje drukowania faktury zaliczkowej z aplikacji POS:

- **Drukowanie faktury zaliczkowej po zawarciu transakcji w aplikacji POS.** Ta opcja jest uruchamiana automatycznie, jeśli faktura zaliczkowa została wygenerowana, a drukarka systemu Windows jest poprawnie skonfigurowana. W takim przypadku zostanie wydrukowana tylko ostatnia faktura zaliczkowa połączona z zamówieniem klienta.
- **Ponowne wydrukowanie faktury zaliczkowej z arkusza transakcji.** Wybierz opcję **Pokaż arkusz**, aby otworzyć arkusz transakcji, znajdź zamówienie odbiorcy, a następnie wybierz opcję **Drukuj fakturę zaliczkową**. W takim przypadku zostaną wydrukowane wszystkie faktury zaliczkowe połączone z zamówieniem klienta.

### <a name="set-up-a-windows-printer"></a>Konfigurowanie drukarki systemu Windows

Wykonaj następujące kroki, aby umożliwić drukowanie dokumentów z aplikacji POS na drukarce systemu Windows podłączonej do stacji sprzętowej.

1. Wybierz kolejno opcje **Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile sprzętu**.
2. Wybierz profil sprzętowy powiązany ze sklepem, w których jest używana drukarka.
3. W sekcji **Drukarka** lub **Drukarka 2** zaktualizuj ustawienia:

    - W polu **Drukarki** zaznacz opcję **Sterownik w systemie Windows**.
    - W polu **Nazwa urządzenia** nadaj drukarce nazwę.

4. Wybierz kolejno opcje **Retail i Commerce \> Retail i Commerce IT \> Harmonogram dystrybucji**.
5. Wybierz zadanie **1090**, a następnie kliknij przycisk **Uruchom teraz**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]