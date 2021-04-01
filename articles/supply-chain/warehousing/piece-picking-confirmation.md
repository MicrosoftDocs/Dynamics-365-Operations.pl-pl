---
title: Potwierdzenie pobrania sztuk
description: W tym temacie opisano sposób konfigurowania i stosowania potwierdzenia pobrania sztuk z urządzenia przenośnego.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 852bd29ae18b4903906aa7fb97a06389cd7cd3bc
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232870"
---
# <a name="piece-picking-confirmation"></a>Potwierdzenie pobrania sztuk

[!include [banner](../includes/banner.md)]

Funkcja pobrania sztuk umożliwia potwierdzanie każdego artykułu w zapasach za pomocą pracy pobrania lub inwentaryzacji na urządzeniu przenośnym. Dla pobrań można potwierdzić ilość pracy do przetworzenia aż do ilości wymienionej w pracy, która ma zostać pobrana. Dla pracy inwentaryzacji pracy można skanować inwentaryzowane zapasy oraz śledzić łączną ilość.

Włączenie funkcji pobrania sztuk powoduje automatyczne zaznaczenie opcji Potwierdzenie produktu. Dla pobrań będących pracą jest włączana maksymalna liczba towarów. Pozwala to ustawić wartość maksymalną w postaci liczby artykułów, które muszą zostać potwierdzone w trakcie procesu pracy. Ilość maksymalna zależy od aktualnie przetwarzanej jednostki roboczej. W pracy typu Inwentaryzacja nie można ustawić wartości maksymalnej.

Można również użyć ilości i jednostki miary (JM) skojarzonej z zeskanowanym kodem kreskowym. Ta funkcjonalność będzie działać w przyjęciach w przepływach przychodzących, w tym przyjęciach spod mieszanych numerów identyfikacyjnych oraz towarów z zamówień zakupu, zamówienia przeniesienia i ładunków. Działa także dla pobrań sztuk, gdzie zeskanowanie kodu kreskowego powoduje dodanie ilości do łącznej liczby potwierdzonych sztuk konwertowanych między jednostką miary kodu kreskowego a jednostką roboczą. Jeśli podczas zliczania w jednostce miary kodu kreskowego potwierdzi się, że ilość jest dozwolona dla inwentaryzacji w grupie sekwencji, ilość zostanie dodana do łącznej liczby.

## <a name="where-it-applies"></a>Zastosowanie

Pobranie sztuk działa dla wszystkich prac inwentaryzacji oraz dla pierwszego pobrania w każdym typie pracy. Pobranie sztuk nie ma zastosowania, gdy towar jest kontrolowany przez numery seryjne lub gdy jest pobraniem do produkcji lub karty Kanban z lokalizacji oznaczonej numerem identyfikacyjnym, a ma ustawiony atrybut lokalizacji tymczasowej.

## <a name="set-up-piece-picking"></a>Konfigurowanie funkcji pobrania sztuk

1.  Na urządzeniu przenośnym w menu otwórz formularz ustawień potwierdzenia pracy: Zarządzanie magazynem > **Zarządzanie magazynem** > **Ustawienia** > **Urządzenie przenośne** > **Elementy menu urządzenia przenośnego**. 
2. Na urządzeniu przenośnym w menu otwórz pozycję Konfiguracja potwierdzenia pracy.

W przypadku pracy typu Pobranie lub Inwentaryzacja są dostępne następujące opcje do wyboru.


|           Opcja           |                                                                            opis                                                                            |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Potwierdzenie pobrania sztuk | Dostępne dla typów prac Pobranie i Inwentaryzacja. Opcja Potwierdzenie produktu jest automatycznie zaznaczona. Umożliwia potwierdzenie każdego artykułu w zapasach z urządzenia przenośnego. |
|  Maksymalna liczba sztuk  |                   Dostępne dla pracy pobrania, jeśli włączono funkcję potwierdzania pobrania sztuk. Ustawia limit liczby sztuk, które należy potwierdzić.                   |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]