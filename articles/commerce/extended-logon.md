---
title: Umożliwia konfigurowanie i korzystanie z funkcji logowania rozszerzonego
description: W tym artykule opisano, jak skonfigurować i używać funkcji rozszerzonego logowania w aplikacji punktu sprzedaży (POS) Microsoft Dynamics 365 Commerce.
author: boycezhu
ms.date: 03/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: boycez
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 92353
ms.assetid: 7473e237-fbc8-41d5-8ba0-920242747488
ms.search.industry: Retail
ms.search.form: RetailFunctionalityProfile
ms.openlocfilehash: e2fc39b1b7fb34f49c061dcc324c28cf5a89277c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283703"
---
# <a name="set-up-and-use-the-extended-logon-capability"></a>Umożliwia konfigurowanie i korzystanie z funkcji logowania rozszerzonego

[!include [banner](includes/banner.md)]

W tym artykule opisano, jak skonfigurować i używać funkcji rozszerzonego logowania w aplikacji punktu sprzedaży (POS) Microsoft Dynamics 365 Commerce.

Cloud POS (CPOS) i Modern POS (MPOS) zapewniają rozszerzone możliwości logowania, które umożliwiają pracownikom sklepów detalicznych logowanie się do aplikacji POS poprzez zeskanowanie kodu kreskowego lub przeciągnięcie karty za pomocą czytnika pasków magnetycznych (MSR).

## <a name="set-up-extended-logon"></a>Konfigurowanie logowania rozszerzonego

Aby skonfigurować logowanie rozszerzone do kas w punktach sprzedaży w sklepie detalicznym, należy wykonać następujące kroki.

1. W Commerce headquarters wybierz kolejno opcje **Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile funkcji**. 
2. W lewym okienku nawigacji wybierz profil funkcji skojarzony ze sklepem detalicznym.
3. Na skróconej **karcie Funkcje**, w obszarze **Opcje uwierzytelniania logowania dodatkowego**, ustaw następujące opcje, **tak** lub **Nie**, zgodnie z potrzebą:

    - **Logowanie się pracowników** — ustaw tę opcję na wartość **Tak**, jeśli chcesz, aby pracownicy logują się do programu POS, zeskanowając kod kreskowy. 
    - **Logowanie za pomocą kodu kreskowego personelu wymaga hasła** — ustaw tę opcję na wartość **Tak**, jeśli chcesz, aby pracownicy wprowadzali hasło podczas logowania się do punktu sprzedaży przez zeskanowanie kodu kreskowego.
    - **Logowanie na kartę personelu** — ustaw tę opcję na wartość **Tak**, jeśli chcesz, aby pracownicy logowali się do punktu sprzedaży, przesuwając kartę.
    - **Logowanie na kartę personelu wymaga hasła** — ustaw tę opcję na wartość **Tak**, jeśli chcesz, aby pracownicy wprowadzali hasło, gdy logują się do punktu sprzedaży, przesuwając kartę.

Kod pocztowy lub karta jest skojarzona z poświadczeniami, które można przypisać do pracownika. Poświadczenia muszą mieć co najmniej sześć znaków. Ciąg zawierający pierwszych pięć znaków musi być unikatowy i traktowany jako *identyfikator poświadczenia* używany do wyszukiwania pracownika. Pozostałe znaki są używane do weryfikacji zabezpieczeń. Na przykład, użytkownik ma dwie karty, z których jedna ma poświadczenia 12345DGIADEYTDW, a jedna z nich ma poświadczenia 12345EWUDZEDAJH. Ponieważ te dwie karty mają ten sam identyfikator poświadczenia, czyli identyfikator 12345, nie można ich pomyślnie przypisać do pracowników.

## <a name="assign-extended-logon"></a>Przypisywanie logowania rozszerzonego

Domyślnie tylko menedżerowie mogą przypisywać pracownikom logowanie rozszerzone. Aby przypisać logowanie rozszerzone, przejdź do opcji **Logowanie rozszerzone** w aplikacji punktu sprzedaży. Następnie wyszukaj pracownika, wpisując jego identyfikator w polu wyszukiwania. Wybierz pracownika, a następnie kliknij przycisk **Przypisz**. Na następnej stronie przeciągnij lub zeskanuj kartę lub kod kreskowy do logowania rozszerzonego, aby przypisać pracownika. Jeśli odczyt danych się powiedzie, przycisk **OK** stanie się aktywny. Kliknij **OK**, aby zapisać logowanie rozszerzone dla tego pracownika.

## <a name="delete-extended-logon"></a>Anulowanie przypisania logowania rozszerzonego

Aby anulować przypisanie logowania rozszerzonego do pracownika, znajdź pracownika za pomocą operacji **Logowanie rozszerzone**. Wybierz pracownika, a następnie kliknij przycisk **Anuluj przypisanie**. Wszystkie poświadczenia logowania rozszerzonego przypisane do tego pracownika są usuwane.

## <a name="use-extended-logon"></a>Używanie logowania rozszerzonego

Po skonfigurowaniu logowania rozszerzonego i przypisaniu pracownikowi kodu kreskowego lub paska magnetycznego pracownik musi tylko przeciągnąć lub zeskanować swoją kartę, gdy wyświetlana jest strona logowania do punktu sprzedaży. Jeśli hasło jest również wymagane przed kontynuowaniem logowania, pracownik zostanie poproszony o wprowadzenie hasła.

## <a name="extend-extended-logon"></a>Rozszerzanie logowania rozszerzonego

Implementacja out-of-box możliwości logowania rozszerzonego wymaga, aby poświadczenia były mieć minimalną długość sześciu znaków oraz aby pierwsze pięć znaków (identyfikator poświadczenia) było unikatowych. Pierwotnie był on przeznaczony jako przykład, dla którego deweloperzy mogli dostosować się do wymagań określonej implementacji. (Na przykład można go dostosować, aby obsługiwał więcej znaków lub używał różnych reguł weryfikacji zabezpieczeń.) Aby uzyskać szczegółowe informacje na temat tworzenia rozszerzeń dla rozszerzonego logowania, zobacz [Rozszerzanie funkcji rozszerzonego logowania dla MPOS i Cloud POS](https://cloudblogs.microsoft.com/dynamics365/no-audience/2018/12/14/extending-the-extended-logon-functionality-for-mpos-and-cloud-pos/).

Usługę logowania też można rozszerzyć o obsługę dodatkowych urządzeń do logowania rozszerzonego, takich jak skanery ręczne. Aby uzyskać więcej informacji, zapoznaj się z [dokumentacją rozszerzania punktu sprzedaży](dev-itpro/pos-extension/pos-extension-overview.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
