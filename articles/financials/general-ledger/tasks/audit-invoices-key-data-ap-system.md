--- 
title: "Wykonywanie audytu faktur i najważniejszych danych w module rozrachunków z dostawcami"
description: "Po otrzymaniu od dostawcy faktury za towary lub usługi na zamówieniu zakupu w procesach biznesowych firmy może być wymagane, aby towary lub usługi zostały dostarczone przed zatwierdzeniem płatności za fakturę."
author: saraschi2
manager: AnnBe
ms.date: 02/16/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 5cd9448c95b7ec0c4a82aca3d21d961259dfb109
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="audit-invoices-and-key-data-in-accounts-payable"></a>Wykonywanie audytu faktur i najważniejszych danych w module rozrachunków z dostawcami

[!include[task guide banner](../../includes/task-guide-banner.md)]

Po otrzymaniu od dostawcy faktury za towary lub usługi na zamówieniu zakupu w procesach biznesowych firmy może być wymagane, aby towary lub usługi zostały dostarczone przed zatwierdzeniem płatności za fakturę. Zanim rozpoczniesz, upewnij się, że wybrano klucz konfiguracji Uzgadnianie faktur. 

Na stronie Parametry modułu rozrachunków z dostawcami upewnij się, że zaznaczono opcję Włącz weryfikację uzgadniania faktur, w polu Księguj fakturę z rozbieżnościami zaznaczono opcję Wymagaj zatwierdzania, a pole Zasady uzgadniania wierszy ma wartość Uzgadnianie trzyelementowe.

Ta procedura wykorzystuje firmę demonstracyjną USMF. Czynności te wykonuje menedżer ds. rozrachunków z dostawcami lub menedżer księgowości.


## <a name="create-a-purchase-order"></a>Tworzenie zamówienia zakupu
1. Przejdź do okna Wszystkie zamówienia zakupu.
2. Kliknij przycisk Nowy.
3. W polu Konto dostawcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. W polu Konto dostawcy wpisz wartość.
5. Kliknij przycisk OK.
6. Kliknij przycisk Dodaj wiersz.
7. W polu Numer towaru wpisz wartość.
8. W okienku akcji kliknij pozycję Zakup.
9. Kliknij przycisk Potwierdź.

## <a name="post-a-product-receipt"></a>Księgowanie dokumentu przyjęcia produktów
1. W okienku akcji kliknij pozycję Odbierz.
2. Kliknij opcję Dokument przyjęcia produktów.
3. Na liście oznacz wybrany wiersz.
4. W polu Dokument przyjęcia produktów wpisz wartość.
5. Kliknij przycisk OK.

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a>Rejestrowanie i uzgadnianie faktury od dostawcy z dokumentem przyjęcia produktów
1. W okienku akcji kliknij pozycję Faktura.
2. Kliknij opcję Faktura.
3. W polu Numer wpisz wartość.
4. Na liście Domyślnie z zaznacz opcję Zamówiona ilość, aby otworzyć rozwijane okno dialogowe.
5. W polu Domyślna ilość dla wierszy zaznacz opcję.
6. Kliknij przycisk OK.
7. Kliknij przycisk Tak.
8. Kliknij opcję Dopasuj dokumenty przyjęcia produktów.
9. Kliknij przycisk OK.
10. W okienku akcji kliknij pozycję Przegląd.
11. Kliknij przycisk Szczegóły uzgadniania.

