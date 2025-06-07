/* See LICENSE file for copyright and license details. */
/* Constants */
#define TERMINAL "st"
#define Z_TERMINAL "wezterm"

/* appearance */
static const unsigned int borderpx  = 1;        /* border pixel of windows */
static const int startwithgaps[]    = { 0 };	/* 1 means gaps are used by default, this can be customized for each tag */
static const unsigned int gappx[]   = { 1 };   /* default gap between windows in pixels, this can be customized for each tag */
static const unsigned int snap      = 20;       /* snap pixel */
static const int swallowfloating    = 0;        /* 1 means swallow floating windows by default */
static const int showbar            = 1;        /* 0 means no bar */
static const int topbar             = 1;        /* 0 means bottom bar */
static const char *fonts[]          = { "monospace:bold:pixelsize=12:antialias=true:autohint=true", "UbuntuMono Nerd Font:size=10:antialias=true:autohint=true", "JoyPixels:pixelsize=10:antialias=true:autohint=true" };
static const char dmenufont[]       = { "mono:pixelsize=14:antialias=true:autohint=true" };
static const char Normfg[]      = "#ebcb8b"; /* layout indicator and status text color #acb4c2 #f5f5dc #d79921 #ebcb8b #999999 #bf616a */
static const char Normbg[]      = "#1d2021"; /* bar color #011627 #011111 #111111 #073642 #222222*/
static const char Normbd[]      = "#444444";
static const char Selbg[]       = "#1d2021"; /* #000000 #005577*/
static const char Selfg[]       = "#ebcb8b"; /* tag and windwo name color #eeeeee */
static const char Selbd[]       = "#1d3b53"; /* active border color #111111 #005577 #0a0f14 #ff0000 #ffff00 #ffffff #fea64c #282c34 #d7d7d7 #02143f */
static const char Titfg[]      = "#d79921"; /* Title indicator and status text color #acb4c2 #f5f5dc #d79921 #ebcb8b #999999 #bf616a */
static const char Titbg[]      = "#011627"; /* bar color #011627 #011111 #111111 #073642 #222222*/
static const char Titbd[]      = "#444444";
static const char col_gray1[]       = "#222222";
static const char col_gray2[]       = "#444444";
static const char col_gray3[]       = "#bbbbbb";
static const char col_gray4[]       = "#eeeeee";
static const char col_cyan[]        = "#005577";
static const unsigned int baralpha = 0.0;
/* static const unsigned int baralpha = 0xd0; */
static const unsigned int borderalpha = OPAQUE;
static const char *colors[][3]      = {
	/*               fg         bg         border   */
	[SchemeNorm] =	 { Normfg, Normbg, Normbd },
	[SchemeSel]  =	 { Selfg, Selbg, Selbd },
	[SchemeTitle]  = { Titfg, Titbg, Titbd },
/*	[SchemeNorm] = { col_gray3, col_gray1, col_gray2 }, */
/*	[SchemeSel]  = { col_gray4, col_cyan,  col_cyan  }, */
};
static const unsigned int alphas[][3]      = {
    /*               fg      bg        border*/
    [SchemeNorm] = { OPAQUE, baralpha, borderalpha },
	[SchemeSel]  = { OPAQUE, baralpha, borderalpha },
};


typedef struct {
	const char *name;
	const void *cmd;
} Sp;
const char *spcmd1[] = {TERMINAL, "-n", "PAD", "-g", "130x22", "-e", "pad_tmux", NULL };
const char *spcmd2[] = {TERMINAL, "-n", "NNN", "-g", "130x22", "-e", "nnn", NULL };
const char *spcmd3[] = {TERMINAL, "-n", "FPRE", "-g", "130x22", "-e", "nnn_tmux", NULL };
const char *spcmd4[] = {TERMINAL, "-n", "MUSIC", "-g", "130x22", "-e", "ncmpcpp", NULL };
const char *spcmd5[] = {"kate", "-s", "notes", NULL };
static Sp scratchpads[] = {
	/* name          cmd  */
	{"PAD",      spcmd1},
	{"NNN",      spcmd2},
	{"FPRE",     spcmd3},
	{"MUSIC",    spcmd4},
	{"KATE",     spcmd5},
};

/* tagging */
static const char *tags[] = { "","","","","","","","","" };
/* static const char *tags[] = { "1", "2", "3", "4", "5", "6", "7", "8", "9" }; */

static const Rule rules[] = {
	/* xprop(1):
	 *	WM_CLASS(STRING) = instance, class
	 *	WM_NAME(STRING) = title
	 */
  /* class                   instance  title               tags mask  isfloating  isterminal  noswallow  monitor */
{ TERMINAL,                  NULL,     NULL,               0,         0,          1,          -1,        -1 },
{ "Gimp",                    NULL,     NULL,               0,         1,          0,           0,        -1 },
{ "Pinentry-gtk-2",          NULL,     NULL,               0,         1,          0,           0,        -1 },

/* browsers */
{ "librewolf",               NULL,     NULL,               1 << 1,    0,          0,          -1,        -1 },
{ "qutebrowser",             NULL,     NULL,               1 << 1,    0,          0,           0,        -1 },
{ "firefox",                 NULL,     NULL,               1 << 1,    1,          0,          -1,        -1 },
{ NULL,		                   "qtfp",   NULL,               0,	        1,		                             -1 },

/* office */
{ "kile",                    NULL,     NULL,               1 << 3,    0,	                               -1 },
{ "libreoffice",             NULL,     NULL,               1 << 3,    0,                       0,        -1 },
{ "Soffice",                 NULL,     NULL,               1 << 3,    0,                       0,        -1 },
{ "libreoffice-startcenter", NULL,     NULL,               1 << 3,    0,                       0,        -1 },

/* media */
{ "mpv",                     NULL,     NULL,               1 << 2,    1,                       1,        -1 },
{ "vlc",                     NULL,     NULL,               1 << 2,    1,                       1,        -1 },
{ "MPlayer",                 NULL,     NULL,               1 << 2,    1,                       1,        -1 },
{ "jamesdsp",                "jamesdsp", NULL,             0,         1,                       1,        -1 },

/* scratchpads */
{ NULL,		                   "PAD",    NULL,               SPTAG(0),  1,			                           -1 },
{ NULL,		                   "NNN",    NULL,               SPTAG(1),  1,			                           -1 },
{ NULL,		                   "FPRE",   NULL,               SPTAG(2),  1,			                           -1 },
{ NULL,                      "MUSIC",  NULL,               SPTAG(3),  1,                       0,        -1 },
{ "kate",                    NULL,     "notes: notes.md ", SPTAG(4),  1,	                               -1 },
};

/* layout(s) */
static const float mfact     = 0.55; /* factor of master area size [0.05..0.95] */
static const int nmaster     = 1;    /* number of clients in master area */
static const int resizehints = 1;    /* 1 means respect size hints in tiled resizals */
static const int lockfullscreen = 1; /* 1 will force focus on the fullscreen window */

static const Layout layouts[] = {
	/* symbol     arrange function */
	{ "[T]",      tile },    /* first entry is default */
	{ "[F]",      NULL },    /* no layout function means floating behavior */
	{ "[M]",      monocle },
	{ "[B]",      bstack },
};



/* key definitions */
#define MODKEY Mod1Mask
#define MOD2   Mod4Mask
#define TAGKEYS(KEY,TAG) \
	{ MODKEY,                       KEY,      view,           {.ui = 1 << TAG} }, \
	{ MODKEY|ControlMask,           KEY,      toggleview,     {.ui = 1 << TAG} }, \
	{ MODKEY|ShiftMask,             KEY,      tag,            {.ui = 1 << TAG} }, \
	{ MODKEY|ControlMask|ShiftMask, KEY,      toggletag,      {.ui = 1 << TAG} },
#define CMD(cmd) { .v = (const char*[]){ "/bin/sh", "-c", cmd, NULL } }

/* helper for spawning shell commands in the pre dwm-5.0 fashion */
#define SHCMD(cmd) { .v = (const char*[]){ "/bin/sh", "-c", cmd, NULL } }
#define STATUSBAR "dwmblocks"

/* commands */
static const char *termcmd[]  = { TERMINAL, NULL };
static const char *termcmd2[]  = { Z_TERMINAL, NULL };
static const char *bcmd[] = { "qutebrowser", NULL };
static const char *bcmd2[] = { "librewolf", NULL };
/* static const char *bcmd2[] = { "firefox", NULL }; */
static const char *bcmd3[] = { TERMINAL, "-e", "elinks", "about://blank", NULL };
static const char *dbang[] = { "dbang", NULL };
static const char *dweb[] = { "dweb", NULL };
static const char *dssr[] = { "dssr", NULL };
static const char *ips[] = { "dwmexit", "suspend", NULL };
static const char *ipr[] = { "dwmexit", "reboot", NULL };
static const char *iph[] = { "dwmexit", "shutdown", NULL };
static const char *ipl[] = { "dwmexit", "lock", NULL };
static const char *pmenu[] = { "powermenu", NULL };
static const char *ssmenu[] = { "maimpick", NULL };
static const char *upvol[] = { "volkeys", "up", NULL };
static const char *downvol[] = { "volkeys", "down", NULL };
static const char *mutevol[] = { "volkeys", "mute", NULL };
static const char *brinc[] = { "blkeys", "up", NULL };
static const char *brdec[] = { "blkeys", "down", NULL };
static const char *broff[] = { "blkeys", "off", NULL };
static char dmenumon[2] = "0"; /* component of dmenucmd, manipulated in spawn() */
static const char *dmenucmd[] = { "dmenu_run", "-i", "-p", ":>_", NULL };

#include <X11/XF86keysym.h>
#include "movestack.c"
#include "shiftview.c"

static Key keys[] = {
/* bar */
	{ MODKEY,                       XK_b,             togglebar,      {0} },
	{ ControlMask,                  XK_semicolon,     spawn,          CMD("tbar") },
/* window */
	{ MODKEY,                       XK_y,             killclient,     {0} },
	{ MODKEY,                       XK_j,             focusstack,     {.i = +1 } },
	{ MODKEY,                       XK_k,             focusstack,     {.i = -1 } },
	{ MODKEY|ShiftMask,             XK_i,             incnmaster,     {.i = +1 } },
	{ MODKEY|ShiftMask,             XK_d,             incnmaster,     {.i = -1 } },
	{ MODKEY,                       XK_h,             setmfact,       {.f = -0.05} },
	{ MODKEY,                       XK_l,             setmfact,       {.f = +0.05} },
	{ MOD2,                         XK_j,             movestack,      {.i = +1 } },
	{ MOD2,                         XK_k,             movestack,      {.i = -1 } },
	{ MODKEY,                       XK_Return,        zoom,           {0} },
/* layout */
	{ MODKEY,                       XK_t,             setlayout,      {.v = &layouts[0]} },
	{ MODKEY,                       XK_f,             setlayout,      {.v = &layouts[1]} },
	{ MODKEY,                       XK_m,             setlayout,      {.v = &layouts[2]} },
	{ MODKEY|ShiftMask,             XK_t,             setlayout,      {.v = &layouts[3]} },
	{ MODKEY,                       XK_space,         setlayout,      {0} },
	{ MODKEY|ShiftMask,             XK_space,         togglefloating, {0} },
	{ MODKEY,                       XK_0,             view,           {.ui = ~0 } },
	{ MODKEY|ShiftMask,             XK_0,             tag,            {.ui = ~0 } },
/* float management */
	/* move float up, down, left, right */
	{ MODKEY,                       XK_KP_Subtract,   moveresize,     {.v = "0x -25y 0w 0h" } },
	{ MODKEY,                       XK_KP_Add,        moveresize,     {.v = "0x 25y 0w 0h" } },
	{ MODKEY,                       XK_KP_Divide,     moveresize,     {.v = "-25x 0y 0w 0h" } },
	{ MODKEY,                       XK_KP_Multiply,   moveresize,     {.v = "25x 0y 0w 0h" } },
	/* resize float up, down, left, right */
	{ MODKEY|ShiftMask,             XK_KP_Subtract,   moveresize,     {.v = "0x 0y 0w -25h" } },
	{ MODKEY|ShiftMask,             XK_KP_Add,        moveresize,     {.v = "0x 0y 0w 25h" } },
	{ MODKEY|ShiftMask,             XK_KP_Divide,     moveresize,     {.v = "0x 0y -25w 0h" } },
	{ MODKEY|ShiftMask,             XK_KP_Multiply,   moveresize,     {.v = "0x 0y 25w 0h" } },
	/* move float to edge */
	{ MODKEY|ControlMask,           XK_KP_Subtract,   moveresizeedge, {.v = "t"} },
	{ MODKEY|ControlMask,           XK_KP_Add,        moveresizeedge, {.v = "b"} },
	{ MODKEY|ControlMask,           XK_KP_Divide,     moveresizeedge, {.v = "l"} },
	{ MODKEY|ControlMask,           XK_KP_Multiply,   moveresizeedge, {.v = "r"} },
	{ MODKEY|ControlMask|ShiftMask, XK_KP_Subtract,   moveresizeedge, {.v = "T"} },
	{ MODKEY|ControlMask|ShiftMask, XK_KP_Add,        moveresizeedge, {.v = "B"} },
	{ MODKEY|ControlMask|ShiftMask, XK_KP_Divide,     moveresizeedge, {.v = "L"} },
	{ MODKEY|ControlMask|ShiftMask, XK_KP_Multiply,   moveresizeedge, {.v = "R"} },
        { MODKEY,                       XK_KP_Enter,      movethrow,      {.ui = DIR_C  }},
    /* { MODKEY,                       XK_q,             movethrow,      {.ui = DIR_N  }},
       { MODKEY,                       KP_2,             movethrow,      {.ui = DIR_S  }},
       { MODKEY,                       XK_a,             movethrow,      {.ui = DIR_W  }},
       { MODKEY,                       XK_g,             movethrow,      {.ui = DIR_E  }}, */
/* monitor */
	{ MODKEY,                       XK_comma,         focusmon,       {.i = -1 } },
	{ MODKEY,                       XK_period,        focusmon,       {.i = +1 } },
	{ MODKEY|ShiftMask,             XK_comma,         tagmon,         {.i = -1 } },
	{ MODKEY|ShiftMask,             XK_period,        tagmon,         {.i = +1 } },
/* tag */
	TAGKEYS(                        XK_1,                             0)
	TAGKEYS(                        XK_2,                             1)
	TAGKEYS(                        XK_3,                             2)
	TAGKEYS(                        XK_4,                             3)
	TAGKEYS(                        XK_5,                             4)
	TAGKEYS(                        XK_6,                             5)
	TAGKEYS(                        XK_7,                             6)
	TAGKEYS(                        XK_8,                             7)
	TAGKEYS(                        XK_9,                             8)
	{ MODKEY,                       XK_Tab,           view,           {0} },
	{ ControlMask,                  XK_space,         view,           {0} },
        { MODKEY|ControlMask,           XK_l,             shiftview,      { .i = +1 } },
        { MODKEY|ControlMask,           XK_h,             shiftview,      { .i = -1 } },
/* power */
	{ MODKEY|ShiftMask,             XK_e,              quit,          {0} },
	{ MODKEY|ShiftMask,             XK_q,              quit,          {1} },
	{ MODKEY|ShiftMask,             XK_x,              spawn,         {.v = pmenu } },
	{ MODKEY|ShiftMask,             XK_s,              spawn,         {.v = ips } },
	{ MODKEY|ShiftMask,             XK_r,              spawn,         {.v = ipr } },
	{ MODKEY|ShiftMask,             XK_h,              spawn,         {.v = iph } },
	{ MODKEY|ShiftMask,             XK_l,              spawn,         {.v = ipl } },
/* terminal */
	{ MODKEY,                       XK_slash,         spawn,          {.v = termcmd } },
	{ MODKEY|ShiftMask,             XK_slash,         spawn,          {.v = termcmd2 } },
/* browsers */
	{ MODKEY,                       XK_i,             spawn,          {.v = bcmd } },
	{ MOD2,                         XK_i,             spawn,          {.v = bcmd2 } },
	{ MODKEY,                       XK_n,             spawn,          {.v = bcmd3 } },
/* menus */
	{ MODKEY,                       XK_semicolon,     spawn,          {.v = dmenucmd } },
	{ MODKEY,                       XK_p,             spawn,          {.v = dweb } },
	{ MOD2,                         XK_p,             spawn,          {.v = dssr } },
	{ MOD2,                         XK_semicolon,     spawn,          {.v = dbang } },
/* scratch pads */
	{ MOD2,                         XK_slash,         togglescratch,  {.ui = 0 } },
	{ MOD2, 			                  XK_n,             togglescratch,  {.ui = 4 } },
	{ MOD2,	                        XK_m,             togglescratch,  {.ui = 3 } },
     /* files */
	{ MOD2, 			                  XK_o,             togglescratch,  {.ui = 2 } },
	{ MODKEY, 			                XK_o,             togglescratch,  {.ui = 1 } },
/* gapps */
	{ ControlMask,                  XK_KP_Subtract,  setgaps,        {.i = -5 } },
	{ ControlMask,                  XK_KP_Add,       setgaps,        {.i = +5 } },
	{ ControlMask|ShiftMask,        XK_KP_Enter,     setgaps,        {.i = GAP_RESET } },
	{ ControlMask|ShiftMask,        XK_KP_Divide,    setgaps,        {.i = GAP_TOGGLE} },
/* exec cmd */
	{ MOD2,                         XK_u,              spawn,         CMD("clipmenu") }, 
	{ 0,                            XF86XK_Calculator, spawn,         CMD("= --dmenu=dmenu -- -l 3 -c") }, /* menu-calc script */
/* media keys */
        { 0,                     XF86XK_MonBrightnessUp,   spawn,         {.v = brinc } },
        { 0,                     XF86XK_MonBrightnessDown, spawn,         {.v = brdec } },
        { 0,                     XF86XK_ScreenSaver,       spawn,         {.v = broff } },
        { 0,                     XF86XK_AudioLowerVolume,  spawn,         {.v = downvol } },
        { 0,                     XF86XK_AudioMute,         spawn,         {.v = mutevol } },
        { 0,                     XF86XK_AudioRaiseVolume,  spawn,         {.v = upvol   } },
/* screen shots */
        { 0,                     XK_Print,   		   spawn,         {.v = ssmenu } },

};


/* statuscmd patch vs dwmblocks */
/*	{ ClkStatusText,        0,              Button1,        sigstatusbar,   {.i = 1} }, */
/*	{ ClkStatusText,        0,              Button2,        sigstatusbar,   {.i = 2} }, */
/*	{ ClkStatusText,        0,              Button3,        sigstatusbar,   {.i = 3} }, */


/* button definitions */
/* click can be ClkTagBar, ClkLtSymbol, ClkStatusText, ClkWinTitle, ClkClientWin, or ClkRootWin */
/* 1-Left, 2-Middle/Shift+Left, 3-Right, 4-Scroll Up/Control+Right, 5-Scroll Down/Control+Left */
static Button buttons[] = {
	/* click                event mask      button          function        argument */
	{ ClkLtSymbol,          0,              Button1,        setlayout,      {0} },
	{ ClkLtSymbol,          0,              Button3,        setlayout,      {.v = &layouts[2]} },
	{ ClkWinTitle,          0,              Button2,        zoom,           {0} },
	{ ClkStatusText,        0,              Button1,        sigstatusbar,   {.i = 1} },
	{ ClkStatusText,        0,              Button3,        sigstatusbar,   {.i = 3} },
	{ ClkStatusText,        ShiftMask,      Button1,        sigstatusbar,   {.i = 2} },
	{ ClkStatusText,        ControlMask,    Button1,        sigstatusbar,   {.i = 5} },
	{ ClkStatusText,        ControlMask,    Button3,        sigstatusbar,   {.i = 4} },
	{ ClkClientWin,         MODKEY,         Button1,        movemouse,      {0} },
	{ ClkClientWin,         MODKEY,         Button2,        togglefloating, {0} },
	{ ClkClientWin,         MODKEY,         Button1,        resizemouse,    {0} },
	{ ClkTagBar,            0,              Button1,        view,           {0} },
	{ ClkTagBar,            0,              Button3,        toggleview,     {0} },
	{ ClkTagBar,            MODKEY,         Button1,        tag,            {0} },
	{ ClkTagBar,            MODKEY,         Button3,        toggletag,      {0} },
};
