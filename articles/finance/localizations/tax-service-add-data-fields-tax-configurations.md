---
title: Dodawanie pól danych w konfiguracjach podatków
description: W tym temacie opisano sposób dostosowywania konfiguracji podatków przez dodanie pól danych.
author: Kai-Cloud
ms.date: 09/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: fb10fb5feb317dca5253eea6e5694a3960a58a7d
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500153"
---
# <a name="add-data-fields-in-tax-configurations"></a>Dodawanie pól danych w konfiguracjach podatków

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób dostosowywania konfiguracji podatków przy użyciu [pól danych dodawanych w integracji podatków](tax-service-add-data-fields-tax-integration-by-extension.md).

## <a name="customize-the-tax-data-model"></a>Dostosuj model danych podatkowych

1. W Microsoft Dynamics 365 Finance przejdź do **Elektroniczne raportowanie** > **Konfiguracje podatku**.
2. W drzewie konfiguracji wybierz **Model danych podatkowych — Europa**. W okienku akcji wybierz **Utwórz konfigurację**.
3. W oknie dialogowym listy rozwijanej wybierz **Model dokumentów podlegających opodatkowaniu uzyskany na podstawie pola Nazwa: Model danych podatkowych — Europa Microsoft**, wprowadź nazwę nowego modelu danych podatkowych, a następnie wybierz pozycję **Utwórz konfigurację**.
4. Wybierz właśnie utworzony model danych podatku, a następnie w okienku akcji wybierz pozycję **Konstruktor**.
5. Rozwiń drzewo modeli danych, zaznacz **Wiersze**, a następnie wybierz **Nowy**.
6. W oknie dialogowym **Tworzenie węzła** wprowadź nazwę, określ typ towaru, a następnie wybierz **Dodaj**.
7. Dodaj wymagane kolumny.
8. W okienku akcji wybierz opcję **Zapisz**, a następnie wybierz opcję **Zakończ**.
9. Zamknij stronę i wyświetl ukończoną wersję modelu danych podatku.

## <a name="customize-the-tax-configuration"></a>Dostosuj konfigurację podatku

1. W Finance przejdź do **Elektroniczne raportowanie** > **Konfiguracje podatku**.
2. W drzewie konfiguracji wybierz **Konfiguracja podatku — Europa**. W okienku akcji wybierz **Utwórz konfigurację**.
3. W oknie dialogowym listy rozwijanej wybierz **Konfiguracja usługi podatkowej pochodząca z nazwy: Konfiguracja podatku — Europa Microsoft**, wprowadź nazwę nowej konfiguracji danych podatkowych, a następnie wybierz pozycję **Utwórz konfigurację**.
4. Wybierz właśnie utworzoną konfigurację podatku, a następnie w okienku akcji wybierz pozycję **Konstruktor**.
5. W sekcji **Właściwości**, w polu **Model danych** wybierz niestandardowy model danych podatkowych utworzony wcześniej.
6. W polu **Wersja modelu danych** wybierz wersję akończoną modelu danych podatku.
7. Wybierz opcję **Dodaj** i dodaj wymagane miary podatku.
8. W okienku akcji wybierz opcję **Zapisz**, a następnie wybierz opcję **Zakończ**.
9. Zamknij stronę i wyświetl ukończoną wersję konfiguracji podatku.

## <a name="implement-tax-features-in-the-customized-tax-configuration"></a>Implementowanie funkcji podatków w dostosowanej konfiguracji podatków

1. W usłudze Regulatory Configuration Service (RCS) przejdź do **Funkcje globalizacji** > **Podatek**.
2. Wybierz **Dodaj**, wprowadź informacje o nowej funkcji, a następnie **Utwórz funkcję**.
3. Na karcie **Wersje** wybierz funkcję, a następnie **Edytuj**.
4. Na karcie **Ogólne** w polu **Wersja konfiguracji** wybierz niestandardową konfigurację i wersję podatku.
5. W oknie dialogowym **Zarządzaj kolumnami** wybierz nagłówek i kolumny wierszy, które chcesz uwzględnić w niestandardowej mierze podatkowej, a następnie wybierz przycisk strzałki w prawo, aby dodać je do listy **Wybrane kolumny**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
