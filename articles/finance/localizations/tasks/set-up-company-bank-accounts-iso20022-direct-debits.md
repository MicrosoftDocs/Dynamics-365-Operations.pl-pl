---
title: Konfigurowanie kont bankowych firmy dla poleceń zapłaty ISO20022
description: To zadanie poprowadzi Cię przez konfigurowanie danych konta bankowego specyficznych dla firmy, które są wymagane do generowania plików płatności od odbiorców.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankAccountTable, OMLegalEntity, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b0faa23193111ed771ccc3a5c7f99ca908a036e9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988143"
---
# <a name="set-up-company-bank-accounts-for-iso20022-direct-debits"></a>Konfigurowanie kont bankowych firmy dla poleceń zapłaty ISO20022

[!include [banner](../../includes/banner.md)]

To zadanie poprowadzi Cię przez konfigurowanie danych konta bankowego specyficznych dla firmy, które są wymagane do generowania plików płatności od odbiorców. Procedura wykorzystuje format zapłaty polecenia zapłaty ISO 20022 jako przykład. Inne formaty mogą wymagać dodatkowych informacji konfiguracyjnych, takich jak identyfikator firmy lub numer rozliczeniowy.



Zadanie utworzono przy użyciu danych firmy demonstracyjnej DEMF.



Jest to druga z pięciu procedur, które razem przedstawiają proces płatności od odbiorców przy użyciu konfiguracji raportowania elektronicznego.


## <a name="set-up-the-iban-and-swift-codes"></a>Konfigurowanie kodów IBAN i SWIFT
1. Wybierz kolejno opcje Zarządzanie gotówką i bankami > Konta bankowe.
2. Użyj szybkiego filtru, aby wyfiltrować pole Konto bankowe według wartości „DEMF OPER”.
3. Na liście kliknij łącze w wybranym wierszu.
    * Na przykład kliknij pozycję „DEMF OPER”, aby otworzyć szczegóły konta bankowego.  
4. Kliknij przycisk Edytuj.
5. Rozwiń lub zwiń sekcję Dodatkowa identyfikacja.
6. W polu IBAN wpisz wartość.
    * Na przykład wpisz „DE89370400440532013000”.  
7. W polu Kod SWIFT wpisz wartość.
    * Na przykład wpisz „DEUTDEFF”.    Należy zauważyć, że kod SWIFT\BIC nie jest obowiązkowy dla wielu formatów płatności, jednak zaleca się zarejestrowanie go dla konta bankowego.  
8. Kliknij przycisk Zapisz.

## <a name="set-up-a-bank-account-for-the-legal-entity"></a>Konfigurowanie konta bankowego firmy
1. Wybierz kolejno opcje Administrowanie organizacją > Organizacje > Firmy.
2. Kliknij przycisk Edytuj.
3. Rozwiń lub zwiń sekcję Informacje o koncie bankowym.
4. W polu Konto bankowe kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Na liście kliknij łącze w wybranym wierszu.
    * Na przykład wybierz konto bankowe „DEMF OPER”.  
6. Kliknij przycisk Zapisz.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]