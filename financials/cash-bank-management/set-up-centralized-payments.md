---
title: "Konfigurowanie scentralizowanych płatności"
description: 
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerInterCompany
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62243
ms.assetid: ffd17b5f-9aea-40e0-be49-d8702f615256
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 44d51807cd6bb64ae2c4bef58d8a445417ffa3a9
ms.openlocfilehash: 815282422a6d7b8eef7d0628cf10b715449e1d1d
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-centralized-payments"></a>Konfigurowanie scentralizowanych płatności



Wykonaj następujące kroki, aby przygotować się do przetwarzania płatności w jednej firmie w imieniu innych firm w Twojej organizacji. Przed rozpoczęciem należy wykonać następujące ustawienia:

-   Utwórz firmy.
-   Ustaw parametry księgi głównej i plany kont.
-   Ustaw parametry rozrachunków z dostawcami i parametry rozrachunków z odbiorcami (w zależności od modułów, w których jest używana funkcja płatności scentralizowane).
-   Skonfiguruj księgowanie międzyfirmowe.

## <a name="set-up-an-organizational-hierarchy-for-centralized-payments"></a>Konfigurowanie hierarchii organizacyjnej na potrzeby płatności scentralizowanych
Konfigurowanie hierarchii organizacyjnej na potrzeby płatności scentralizowanych jest konieczne. Do przetwarzania scentralizowanych płatności dostawców i odbiorców jest używana ta sama hierarchia organizacyjna. **Uwaga:** Struktura hierarchii nie ma znaczenia w przypadku scentralizowanych płatności. Dowolna firma w hierarchii będzie mogła przetwarzać płatności w imieniu dowolnej innej firmy w hierarchii. Na stronie **hierarchii organizacyjnych** można utworzyć nową hierarchię organizacyjną.

## <a name="set-up-an-intercompany-account-for-centralized-payments"></a>Konfigurowanie księgowania międzyfirmowego na potrzeby płatności scentralizowanych
Gdy transakcje płatności w bieżącej firmie są rozliczane za pomocą faktur w innych firmach, dla każdej firmy są tworzone odpowiednie transakcje zobowiązań i należności. Należy określić firmę, dla której są księgowane kwoty rabatu gotówkowego oraz zrealizowane dodatnie lub ujemne różnice kursowe. Przed rozpoczęciem określ firmę używaną w przetwarzaniu płatności odbiorcy i dostawcy. Jeśli jedna firma przetwarza płatności dostawcy, a inna płatności odbiorcy, trzeba będzie przełączyć na każdą z firm. Na **księgowania międzyfirmowego** strony, można wybrać rekord relacji międzyfirmowych dla podmiotu prawnego, który będzie przetwarzał płatności w imieniu firmy. Na **scentralizowane płatności** kartę, można wybrać, czy do księgowania środków pieniężnych rabaty na podmiot prawny płatności (lub innych transakcji, która zmniejsza saldo konta dostawcy) lub podmiot prawny faktury (lub innych transakcji, która zwiększa saldo konta dostawcy). Ten wybór funkcjonuje w powiązaniu z polem **Zarządzanie rabatami gotówkowymi** na stronach **parametrów rozrachunków z dostawcami** i **parametrów rozrachunków z odbiorcami**. W wypadku nadpłat i rozbieżności dla różnic groszowych jest używane ustawienie firmy obsługującej płatności. W wypadku niedopłat i rozbieżności dla różnic groszowych jest używane ustawienie firmy obsługującej fakturowanie.

## <a name="map-vendor-accounts-across-legal-entities"></a>Mapowanie kont dostawcy na firmy
Jeśli płacisz dostawcy z jednej firmy i chcesz wybrać faktury dla tego dostawcy w innych firmach, musisz się upewnić, że wszystkie odpowiednie konta dostawcy w każdej firmie używają tego samego identyfikatora książki adresowej. Jeśli otrzymujesz płatności odbiorcy, który płaci faktury w więcej niż jednej firmie, to musisz dopilnować, by w odniesieniu do wszystkich odpowiednich kont odbiorcy w każdej firmie były używane te same identyfikatory książki adresowej.

## <a name="set-up-posting-profiles-for-centralized-payments"></a>Konfigurowanie profilów księgowania na potrzeby płatności scentralizowanych
Gdy w jednej firmie tworzysz płatność, która skutkuje rozliczeniem faktur w innych firmach, wówczas w każdej firmie musi być używany ten sam identyfikator profilu księgowania. Aby zapewnić poprawne utworzenie płatności, w każdej firmie obsługującej fakturowanie skonfiguruj profil księgowania odpowiadający profilom księgowania używanym w firmie obsługującej płatności. Przełącz się do pierwszej osoby prawnej faktury, a następnie, na **temat Vendor posting profiles** stronę, można utworzyć nowy profil księgowania lub Edytuj istniejący profil księgowania. Opcje, które mają być dla profilu księgowania w firmie faktury nie muszą być zgodne z konfiguracją profilu księgowania w firmie płatności.

## <a name="set-up-methods-of-payment-for-centralized-payments"></a>Konfigurowanie metod płatności na potrzeby płatności scentralizowanych
Gdy w jednej firmie tworzysz płatność, która skutkuje rozliczeniem faktur w innych firmach, wówczas w każdej firmie musi być używany ten sam identyfikator metody płatności. Aby zapewnić poprawne utworzenie płatności, w każdej firmie obsługującej fakturowanie skonfiguruj metodę płatności odpowiadającą metodom płatności używanym w firmie obsługującej płatności. Przełącz do pierwszej firmy obsługującej fakturę, a następnie na stronie **Metody płatności ** można utworzyć nową metodę płatności lub edytować istniejącą metodę płatności. Opcje wybrane w przypadku metody płatności firmy obsługującej fakturowanie nie muszą się zgadzać z konfiguracją metody płatności w firmie obsługującej płatności.

## <a name="set-up-default-descriptions"></a>Ustawianie opisów domyślnych
Można zdefiniować domyślne opisy dla załączników rozliczeń międzyfirmowych. Domyślny opis jest dołączany do transakcji „należne do” i „należne od” w trakcie procesu rozliczeń międzyfirmowych. Na stronie **Opisy domyślne** można tworzyć nowe opisy dla **rozliczenia z odbiorcą międzyfirmowym **i **rozliczenia z dostawcą międzyfirmowym** poprzez wybranie języka i wprowadzenie tekstu.


