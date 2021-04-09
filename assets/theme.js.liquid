var Twitter,
  slice = [].slice,
  extend = function(child, parent) { for (var key in parent) { if (hasProp.call(parent, key)) child[key] = parent[key]; } function ctor() { this.constructor = child; } ctor.prototype = parent.prototype; child.prototype = new ctor(); child.__super__ = parent.prototype; return child; },
  hasProp = {}.hasOwnProperty;

window.ThemeUtils = {
  extend: function() {
    var dest, j, k, len, obj, objs, v;
    dest = arguments[0], objs = 2 <= arguments.length ? slice.call(arguments, 1) : [];
    for (j = 0, len = objs.length; j < len; j++) {
      obj = objs[j];
      for (k in obj) {
        v = obj[k];
        dest[k] = v;
      }
    }
    return dest;
  },
  windowWidth: function() {
    var documentWidth, width, windowWidth;
    documentWidth = document.documentElement.clientWidth;
    windowWidth = window.innerWidth;
    width = documentWidth < windowWidth ? windowWidth : documentWidth;
    return width;
  },
  debounce: function(func, wait, immediate) {
    var timeout;
    timeout = null;
    return function() {
      var args, callNow, context, later;
      context = this;
      args = arguments;
      later = function() {
        timeout = null;
        if (!immediate) {
          func.apply(context, args);
        }
      };
      callNow = immediate && !timeout;
      clearTimeout(timeout);
      timeout = setTimeout(later, wait);
      if (callNow) {
        func.apply(context, args);
      }
    };
  },
  inViewport: function(el) {
    var rect, viewportHeight, viewportWidth;
    if (typeof jQuery === "function" && el instanceof jQuery) {
      el = el[0];
    }
    rect = el.getBoundingClientRect();
    if (document.documentElement.clientWidth < window.innerWidth) {
      viewportWidth = document.documentElement.clientWidth;
    } else {
      viewportWidth = window.innerHeight;
    }
    if (document.documentElement.clientHeight < window.innerHeight) {
      viewportHeight = document.documentElement.clientHeight;
    } else {
      viewportHeight = window.innerHeight;
    }
    return rect.bottom >= 0 && rect.right >= 0 && rect.top <= viewportHeight && rect.left <= viewportWidth;
  },
  externalLinks: function($el) {
    var anchors;
    anchors = $el.find('a[href^="http"]').filter((function(_this) {
      return function(i, el) {
        return el.href.indexOf(location.hostname) === -1;
      };
    })(this));
    return anchors.attr('target', '_blank');
  },
  unique: function(array) {
    var j, key, output, ref, results, value;
    output = {};
    for (key = j = 0, ref = array.length; 0 <= ref ? j < ref : j > ref; key = 0 <= ref ? ++j : --j) {
      output[array[key]] = array[key];
    }
    results = [];
    for (key in output) {
      value = output[key];
      results.push(value);
    }
    return results;
  },
  scrollTarget: function($el) {
    if (!($el instanceof jQuery)) {
      $el = $($el);
    }
    return $('html, body').animate({
      scrollTop: $el.offset().top
    }, 500, 'linear');
  }
};

window.AccordionView = (function(superClass) {
  extend(AccordionView, superClass);

  function AccordionView() {
    return AccordionView.__super__.constructor.apply(this, arguments);
  }

  AccordionView.prototype.events = {
    'click [data-accordion-trigger]': '_toggle'
  };

  AccordionView.prototype.initialize = function() {
    this.accordionContent = '[data-accordion-content]';
    this.accordionTrigger = '[data-accordion-trigger]';
    this.activeAccordion = 'accordion-active';
    return this.sectionBinding();
  };

  AccordionView.prototype.sectionBinding = function() {
    this.$el.on('shopify:section:load', (function(_this) {
      return function() {
        return _this.delegateEvents();
      };
    })(this));
    this.$el.on('shopify:section:unload', (function(_this) {
      return function() {
        return _this.undelegateEvents();
      };
    })(this));
    return this.$el.on('shopify:block:select', (function(_this) {
      return function(event) {
        var $container, $target;
        $container = $(event.target);
        $target = $container.find(_this.accordionTrigger);
        if (!$target.hasClass(_this.activeAccordion)) {
          return $target.trigger('click');
        }
      };
    })(this));
  };

  AccordionView.prototype._toggle = function(event) {
    var $content, $target, trigger;
    event.preventDefault();
    $target = $(event.currentTarget);
    trigger = $target.attr('data-accordion-trigger');
    $content = $("[data-accordion-content=" + trigger + "]");
    if ($target.hasClass(this.activeAccordion)) {
      return this._close($target, $content);
    } else {
      this._closeAll();
      return this._open($target, $content);
    }
  };

  AccordionView.prototype._closeAll = function() {
    return $(this.accordionTrigger).each((function(_this) {
      return function(index, accordion) {
        var $target;
        $target = $(accordion);
        if ($target.hasClass(_this.activeAccordion)) {
          return $target.trigger('click');
        }
      };
    })(this));
  };

  AccordionView.prototype._open = function($target, $content) {
    return $content.slideDown({
      start: (function(_this) {
        return function() {
          return $target.addClass(_this.activeAccordion);
        };
      })(this)
    });
  };

  AccordionView.prototype._close = function($target, $content) {
    return $content.slideUp({
      start: (function(_this) {
        return function() {
          return $target.removeClass(_this.activeAccordion);
        };
      })(this)
    });
  };

  return AccordionView;

})(Backbone.View);

window.NavigationView = (function(superClass) {
  extend(NavigationView, superClass);

  function NavigationView() {
    return NavigationView.__super__.constructor.apply(this, arguments);
  }

  NavigationView.prototype.events = {
    'click .header-drawer .has-dropdown > a .dropdown-toggle': 'toggleNavigation'
  };

  NavigationView.prototype.initialize = function() {
    this.megaNav = this.$('.mega-nav');
    this.secondaryTier = this.megaNav.find('.secondary');
    return $(document.body).on('click', (function(_this) {
      return function(e) {
        if (!$(e.target).closest('.navigation').length) {
          _this.$('.navigation .open').removeClass('open');
          if (_this.megaNav.length) {
            return _this.resetMegaNav();
          }
        }
      };
    })(this));
  };

  NavigationView.prototype.toggleNavigation = function(e) {
    var button, megaNavHeight, target;
    e.preventDefault();
    target = $(e.currentTarget);
    button = $(e.currentTarget).children('.dropdown-toggle');
    if (target.hasClass('dropdown-toggle')) {
      button = target;
      target = target.parent();
    }
    megaNavHeight = this.megaNav.outerHeight();
    if (target.parent().hasClass('has-dropdown')) {
      e.preventDefault();
      if (target.hasClass('main-nav-item') && target.parent().hasClass('has-mega-nav')) {
        if (target.parent().hasClass('open')) {
          this.resetMegaNav();
          this.$('.navigation li').removeClass('open');
        } else {
          this.$('.navigation li').removeClass('open');
          target.parent().addClass('open');
        }
      } else if (target.hasClass('main-nav-item') && target.parent().hasClass('simple-dropdown')) {
        if (target.parent().hasClass('open')) {
          this.$('.navigation li').removeClass('open');
        } else {
          this.resetMegaNav();
          this.$('.navigation li').removeClass('open');
          target.parent().addClass('open');
        }
      } else {
        target.parent().toggleClass('open');
      }
      return button.attr('aria-expanded', target.parent().hasClass('open'));
    }
  };

  NavigationView.prototype.resetMegaNav = function() {
    return setTimeout((function(_this) {
      return function() {
        _this.megaNav.height('auto');
        return _this.secondaryTier.removeClass('hide');
      };
    })(this), 200);
  };

  NavigationView.prototype.render = function() {};

  return NavigationView;

})(Backbone.View);

window.HeaderView = (function() {
  function HeaderView() {
    this.window = $(window);
    this.$document = $(document.body);
    this.el = '[data-main-header]';
    this.headerLogo = '[data-header-logo]';
    this._init();
  }

  HeaderView.prototype._init = function() {
    this.$el = $(this.el);
    this.$drawerMenu = this.$document.find('[data-header-drawer]');
    this.$mainContent = $('[data-main-content]');
    this.$mainHeader = this.$el.find('[data-header-content]');
    this.$headerLogo = $(this.headerLogo);
    this.$searchWrapper = this.$el.find('[data-header-search]');
    this.slideShow = '[data-section-type=slideshow]';
    this.$slideShow = $(this.slideShow);
    this.isHeaderNavigation = this.$el.attr('data-main-header') === 'header';
    this.hasLogo = this.$el.find(this.headerLogo).length;
    this.isHeaderSticky = this.$el.attr('data-sticky-header') != null;
    this.sectionChanges(this.$slideShow, false, null);
    this._bindEvents();
    this.navigation = new NavigationView({
      el: this.$document
    });
    if (this.isHeaderNavigation) {
      this.calculateHeaderWidths();
      this.window.resize((function(_this) {
        return function() {
          return _this.fitHeader();
        };
      })(this));
    }
    if ($('html').hasClass('lt-ie9')) {
      this.verticallyCenterShopName();
      if (this.hasLogo) {
        return this.verticallyCenterLogo();
      }
    }
  };

  HeaderView.prototype._bindEvents = function() {
    this.$document.on('shopify:section:select.header', (function(_this) {
      return function(event) {
        return _this.sectionChanges(null, true, event.originalEvent.detail.sectionId);
      };
    })(this)).on('shopify:section:deselect.header', (function(_this) {
      return function(event) {
        return _this.sectionChanges(null, true, event.originalEvent.detail.sectionId);
      };
    })(this)).on('click', '.header-search-toggle', (function(_this) {
      return function() {
        return _this.openSearch();
      };
    })(this)).on('blur', '.header-search-input', (function(_this) {
      return function() {
        return _this.closeSearch();
      };
    })(this)).on('click', '[data-drawer-toggle]', (function(_this) {
      return function() {
        return _this.toggleCollapsedNav();
      };
    })(this)).on('toggleStickyHeader', (function(_this) {
      return function(event, $slideshow) {
        return _this.stickyHeader($slideshow);
      };
    })(this)).on('toggleSlideShowHeader', (function(_this) {
      return function(event, $slideshow) {
        return _this.slideShowHeader($slideshow);
      };
    })(this)).on('swapLogo', (function(_this) {
      return function() {
        return _this.swapLogo();
      };
    })(this)).on('mouseenter', '.has-dropdown', (function(_this) {
      return function(event) {
        return _this.openSubNav(event);
      };
    })(this)).on('mouseleave', '.has-dropdown', (function(_this) {
      return function(event) {
        return _this.closeSubNav(event);
      };
    })(this));
    return this.window.on('resize.header', (function(_this) {
      return function() {
        return _this._resizeEvents();
      };
    })(this));
  };

  HeaderView.prototype.unBindEvents = function() {
    this.$document.off('shopify:section:select.header').off('shopify:section:deselect.header').off('.header-search-toggle').off('blur', '.header-search-input').off('click', '[data-drawer-toggle]').off('toggleStickyHeader', this.el).off('toggleSlideShowHeader', this.el).off('swapLogo', this.el);
    this.navigation.undelegateEvents();
    return this.window.off('resize.header');
  };

  HeaderView.prototype._resizeEvents = function() {
    this.stickyHeaderOffset(this.isHeaderSticky);
    if (this.$document.hasClass('navigation-below-header')) {
      this.$document.removeClass('navigation-below-header');
      this.$('.main-header').addClass('collapsed-navigation');
    }
    if (window.ThemeUtils.windowWidth() > 720 && this.$document.hasClass('showing-drawer')) {
      if (this.$document.hasClass('navigation-below-header') || this.$document.hasClass('navigation-header') && !this.$('.main-header').hasClass('collapsed-navigation')) {
        this.toggleCollapsedNav();
      }
    }
    return this.swapLogo();
  };

  HeaderView.prototype.swapLogo = function() {
    var hasFullBleedSlideshow, windowWidth;
    if (!this.$headerLogo.length) {
      return;
    }
    windowWidth = window.ThemeUtils.windowWidth();
    hasFullBleedSlideshow = $('[data-full-bleed-slideshow]').length;
    if (windowWidth <= 720 || !hasFullBleedSlideshow || this.$el.hasClass('sticky-header-scrolled')) {
      this.$headerLogo.attr('src', this.$headerLogo.attr('data-src-original'));
      return this.$headerLogo.attr('srcset', this.$headerLogo.attr('data-src-original'));
    } else if (hasFullBleedSlideshow) {
      this.$headerLogo.attr('src', this.$headerLogo.attr('data-src-alt'));
      return this.$headerLogo.attr('srcset', this.$headerLogo.attr('data-src-alt'));
    }
  };

  HeaderView.prototype.getColorSetting = function() {
    var colorSetting;
    colorSetting = this.$el.attr('class').match(/header-bleed-.+-colors/);
    if (colorSetting != null) {
      return colorSetting[0];
    } else {
      return false;
    }
  };

  HeaderView.prototype.slideShowHeader = function($slideShow) {
    if ($slideShow == null) {
      $slideShow = $(this.slideShow);
    }
    if ($slideShow.length && ($slideShow.attr('data-full-bleed-slideshow') != null)) {
      return this.$el.addClass('full-bleed-slideshow');
    } else {
      this.$el.removeClass('full-bleed-slideshow');
      return this.$el.removeClass(this.getColorSetting());
    }
  };

  HeaderView.prototype.stickyHeader = function($slideShow) {
    var colorSetting, hasSlideshow;
    if ($slideShow == null) {
      $slideShow = $(this.slideShow);
    }
    this.stickyHeaderOffset(this.isHeaderSticky, $slideShow);
    if (!this.isHeaderSticky) {
      return;
    }
    hasSlideshow = $slideShow.attr('data-full-bleed-slideshow') != null;
    colorSetting = this.getColorSetting();
    if (hasSlideshow && colorSetting) {
      this.$el.attr('data-header-bleed-color', colorSetting);
    }
    return this.window.on('scroll', (function(_this) {
      return function(e) {
        var scrollPosition;
        scrollPosition = _this.window.scrollTop();
        scrollPosition = scrollPosition < 110 ? 0 : scrollPosition;
        if (scrollPosition > 0) {
          _this.$el.removeClass('full-bleed-slideshow').addClass('sticky-header-scrolled');
          if (hasSlideshow) {
            _this.$el.removeClass(colorSetting);
          }
        } else if (scrollPosition === 0) {
          _this.$el.removeClass('sticky-header-scrolled');
          if (hasSlideshow) {
            _this.$el.addClass('full-bleed-slideshow').addClass(_this.$el.attr('data-header-bleed-color'));
          } else {
            _this.$el.removeClass('full-bleed-slideshow');
          }
        }
        return _this.swapLogo();
      };
    })(this));
  };

  HeaderView.prototype.stickyHeaderOffset = function(toggleOn, $slideShow) {
    var $promotionBar, $slides, hasFullBleedSlideshow, hasSlideshow, offsetHeight, promotionBarHeight, slideOffset;
    if ($slideShow == null) {
      $slideShow = $(this.slideShow);
    }
    offsetHeight = this.$el.outerHeight();
    $promotionBar = this.$el.find('[data-promotion-bar]');
    hasFullBleedSlideshow = ($slideShow != null ? $slideShow.attr('data-full-bleed-slideshow') : void 0) != null;
    hasSlideshow = $slideShow != null ? $slideShow.length : void 0;
    if (hasSlideshow) {
      $slides = $slideShow.find('[data-slide]');
      $slideShow.css({
        paddingTop: '',
        marginTop: ''
      });
      if ($slides.length) {
        $slides.css({
          paddingTop: '',
          height: ''
        });
        if (!hasFullBleedSlideshow || window.ThemeUtils.windowWidth() < 720) {
          $slides.find('.slide-text').css({
            paddingTop: '',
            paddingBottom: ''
          });
        }
      }
    }
    this.$mainContent.css({
      paddingTop: '',
      marginTop: ''
    });
    if (!((toggleOn || hasFullBleedSlideshow) && window.ThemeUtils.windowWidth() > 720)) {
      return;
    }
    if (hasSlideshow) {
      if (hasFullBleedSlideshow) {
        slideOffset = offsetHeight + 50;
        if ($promotionBar.length) {
          promotionBarHeight = $promotionBar.outerHeight();
          slideOffset = slideOffset - promotionBarHeight;
          this.$mainContent.css({
            paddingTop: promotionBarHeight
          });
        }
        $slides.find('.slide-text').css({
          paddingTop: slideOffset,
          paddingBottom: 100
        });
      } else {
        if ($slideShow.attr('data-product-slideshow') != null) {
          offsetHeight = offsetHeight + 20;
        }
        $slideShow.css({
          marginTop: offsetHeight
        });
      }
      return $slideShow.find('[data-slideshow-container]').trigger('heightUpdate');
    } else {
      if ($('.template-index .module-container').length) {
        return this.$mainContent.css({
          paddingTop: offsetHeight
        });
      } else {
        return this.$mainContent.css({
          marginTop: offsetHeight
        });
      }
    }
  };


  /*
      Check to see if the header needs a border beneath it
          - Only apply border if
              - There is no slideshow
              - Header background matches body background
              - The first occurrence of '.module-container' has the default style
   */

  HeaderView.prototype.borderCheck = function() {
    var $mainHeader, bodyBackground, headerBackground;
    $mainHeader = $('[data-main-header]');
    if (Theme.headerSticky || $('[data-section-type=slideshow]').length !== 0) {
      return;
    }
    if ($(document.body).css('background-image') === !'none') {
      return;
    }
    headerBackground = $mainHeader.css('background-color');
    bodyBackground = $(document.body).css('background-color');
    if ($('.module-container:first').hasClass('default-style') && headerBackground === bodyBackground) {
      return $mainHeader.toggleClass('show-border', true);
    } else {
      return $mainHeader.toggleClass('show-border', false);
    }
  };


  /*
      These events need to fire when any section in the TE is reloaded
   */

  HeaderView.prototype.sectionChanges = function($slideshow, isDocumentEvent, sectionId) {
    if (isDocumentEvent && sectionId === 'general-header') {
      return;
    }
    this.borderCheck();
    this.stickyHeader($slideshow);
    this.slideShowHeader($slideshow);
    return this.$headerLogo.on("rimg:load", (function(_this) {
      return function() {
        return _this.swapLogo();
      };
    })(this));
  };

  HeaderView.prototype.calculateHeaderWidths = function() {
    return this.$el.imagesLoaded((function(_this) {
      return function() {
        var brandingWidth, toolsWidth;
        brandingWidth = _this.$el.find('.branding').outerWidth(true);
        toolsWidth = _this.$el.find('.header-tools').outerWidth(true);
        if (brandingWidth === 0 && _this.$headerLogo.length) {
          brandingWidth = _this.$headerLogo.width();
        }
        _this.combinedWidth = brandingWidth + toolsWidth;
        return _this.fitHeader();
      };
    })(this));
  };

  HeaderView.prototype.fitHeader = function() {
    var headerWidth;
    headerWidth = this.$mainHeader.width();
    this.$mainHeader.toggleClass('collapsed-navigation', this.combinedWidth + 45 > headerWidth);
    return this.stickyHeaderOffset(this.isHeaderSticky, null);
  };

  HeaderView.prototype.toggleCollapsedNav = function(e) {
    if (e) {
      e.stopPropagation();
      e.preventDefault();
    }
    this.$document.toggleClass('showing-drawer');
    if (Modernizr.csstransitions) {
      return this.$el.one('transitionend', (function(_this) {
        return function() {
          return _this.$document.toggleClass('drawer-visible');
        };
      })(this));
    } else {
      return this.$document.toggleClass('drawer-visible');
    }
  };

  HeaderView.prototype.openSearch = function() {
    if (window.innerWidth <= 720) {
      window.location.href = '/search';
      return;
    }
    this.$searchWrapper.addClass('active').find('input').focus();
    return this.$searchWrapper.on('keyup.search', (function(_this) {
      return function(e) {
        if (e.keyCode === 27) {
          return _this.closeSearch();
        }
      };
    })(this));
  };

  HeaderView.prototype.closeSearch = function() {
    return this.$searchWrapper.removeClass('active').off('keyup.search');
  };

  HeaderView.prototype.verticallyCenterLogo = function() {
    return this.$el.imagesLoaded((function(_this) {
      return function() {
        var logoHeight;
        logoHeight = _this.$headerLogo.height();
        return _this.$('a.logo img').css({
          marginTop: -1 * logoHeight / 2
        });
      };
    })(this));
  };

  HeaderView.prototype.verticallyCenterShopName = function() {
    var shopNameHeight;
    shopNameHeight = this.$drawerMenu.find('h1 a').height();
    return this.$drawerMenu.find('h1 a').css({
      marginTop: -1 * shopNameHeight / 2
    });
  };

  HeaderView.prototype.openSubNav = function(e) {
    this.checkSubNavVisibillity(e);
    return this.setExpanded(e);
  };

  HeaderView.prototype.closeSubNav = function(e) {
    return this.unsetExpanded(e);
  };

  HeaderView.prototype.checkSubNavVisibillity = function(e) {
    var $subNav, $subNavPosition;
    $subNav = $(e.currentTarget).children('ul').eq(0);
    if ($subNav.length) {
      $subNavPosition = $subNav.offset().left + $subNav.outerWidth();
      if ($subNavPosition > $(window).width()) {
        return $subNav.addClass('open-right');
      }
    }
  };

  HeaderView.prototype.setExpanded = function(e) {
    var $link;
    $link = $(e.currentTarget).find('.dropdown-toggle');
    return $link.attr("aria-expanded", true);
  };

  HeaderView.prototype.unsetExpanded = function(e) {
    var $link;
    $link = $(e.currentTarget).find('.dropdown-toggle');
    return $link.attr("aria-expanded", false);
  };

  HeaderView.prototype.render = function() {};

  return HeaderView;

})();

window.ImagesWithText = (function(superClass) {
  extend(ImagesWithText, superClass);

  function ImagesWithText() {
    return ImagesWithText.__super__.constructor.apply(this, arguments);
  }

  ImagesWithText.prototype.initialize = function() {
    this.$window = $(window);
    this.centerText(this.$el);
    return this.$window.on('resize.images-with-text', window.ThemeUtils.debounce((function(_this) {
      return function() {
        return _this.centerText(_this.$el);
      };
    })(this), 10));
  };

  ImagesWithText.prototype.prepareRemove = function() {
    return this.$window.off('resize.images-with-text');
  };

  ImagesWithText.prototype.centerText = function($container) {
    var $content, containerHeight, contentHeight;
    $container.css({
      minHeight: ''
    });
    if ($container.attr('data-image-with-text-layout') !== 'background') {
      return;
    }
    $content = $container.find('[data-feature-content]');
    containerHeight = $container.outerHeight(true);
    contentHeight = $content.outerHeight(true);
    if (containerHeight > contentHeight) {
      return $content.css({
        top: (containerHeight - contentHeight) / 2
      });
    } else {
      $content.css({
        top: ''
      });
      return $container.css({
        minHeight: contentHeight
      });
    }
  };

  return ImagesWithText;

})(Backbone.View);

window.ZoomView = (function(superClass) {
  extend(ZoomView, superClass);

  function ZoomView() {
    return ZoomView.__super__.constructor.apply(this, arguments);
  }

  ZoomView.prototype.events = {
    'prepare-zoom': 'prepareZoom',
    'click': 'toggleZoom',
    'mouseout .product-image-zoom': 'toggleZoom',
    'mousemove .product-image-zoom': 'zoomImage'
  };

  ZoomView.prototype.initialize = function() {
    this.zoomArea = this.$('.product-image-zoom');
    this.$newImage = null;
    return this.$el.imagesLoaded((function(_this) {
      return function() {
        return _this.prepareZoom();
      };
    })(this));
  };

  ZoomView.prototype.prepareZoom = function() {
    var newImage, photoAreaHeight, photoAreaWidth;
    photoAreaWidth = this.$el.width();
    photoAreaHeight = this.$el.height();
    newImage = new Image();
    this.$newImage = $(newImage);
    this.$newImage.on('load', (function(_this) {
      return function() {
        var ratio, ratios;
        _this.zoomImageWidth = newImage.width;
        _this.zoomImageHeight = newImage.height;
        ratios = new Array();
        ratios[0] = _this.zoomImageWidth / photoAreaWidth;
        ratios[1] = _this.zoomImageHeight / photoAreaHeight;
        ratio = Math.max.apply(Math, ratios);
        if (ratio < 1.4) {
          _this.$el.removeClass('zoom-enabled');
        } else {
          _this.$el.addClass('zoom-enabled');
          return _this.zoomArea.css({
            backgroundImage: "url(" + newImage.src + ")"
          });
        }
      };
    })(this));
    return newImage.src = this.$('img').attr('src');
  };

  ZoomView.prototype.toggleZoom = function(e) {
    if (this.$el.hasClass('zoom-enabled')) {
      if (e.type === 'mouseout') {
        this.zoomArea.removeClass('active');
        return;
      }
      if (this.zoomArea.hasClass('active')) {
        this.zoomArea.removeClass('active');
      } else {
        this.zoomArea.addClass('active');
      }
      return this.zoomImage(e);
    }
  };

  ZoomView.prototype.zoomImage = function(e) {
    var bigImageOffset, bigImageX, bigImageY, mousePositionX, mousePositionY, newBackgroundPosition, ratioX, ratioY, zoomHeight, zoomWidth;
    zoomWidth = this.zoomArea.width();
    zoomHeight = this.zoomArea.height();
    bigImageOffset = this.$el.offset();
    bigImageX = Math.round(bigImageOffset.left);
    bigImageY = Math.round(bigImageOffset.top);
    mousePositionX = e.pageX - bigImageX;
    mousePositionY = e.pageY - bigImageY;
    if (mousePositionX < zoomWidth && mousePositionY < zoomHeight && mousePositionX > 0 && mousePositionY > 0) {
      if (this.zoomArea.hasClass('active')) {
        ratioX = Math.round(mousePositionX / zoomWidth * this.zoomImageWidth - zoomWidth / 2) * -1;
        ratioY = Math.round(mousePositionY / zoomHeight * this.zoomImageHeight - zoomHeight / 2) * -1;
        if (ratioX > 0) {
          ratioX = 0;
        }
        if (ratioY > 0) {
          ratioY = 0;
        }
        if (ratioX < -(this.zoomImageWidth - zoomWidth)) {
          ratioX = -(this.zoomImageWidth - zoomWidth);
        }
        if (ratioY < -(this.zoomImageHeight - zoomHeight)) {
          ratioY = -(this.zoomImageHeight - zoomHeight);
        }
        newBackgroundPosition = ratioX + "px " + ratioY + "px";
        return this.zoomArea.css({
          backgroundPosition: newBackgroundPosition
        });
      }
    }
  };

  ZoomView.prototype.prepareRemove = function() {
    return this.$newImage.off('load');
  };

  return ZoomView;

})(Backbone.View);

window.LinkedOptions = (function() {
  function LinkedOptions(options) {
    this.options = options;
    this._init();
  }

  LinkedOptions.prototype._init = function() {
    return this._mapVariants(this.options.productJSON);
  };

  LinkedOptions.prototype._getCurrent = function(optionIndex) {
    var key, option1, option2, selector;
    if (this.options.type === 'select') {
      switch (optionIndex) {
        case 0:
          key = 'root';
          selector = this.options.$selector.eq(0);
          break;
        case 1:
          key = this.options.$selector.eq(0).val();
          selector = this.options.$selector.eq(1);
          break;
        case 2:
          key = (this.options.$selector.eq(0).val()) + " / " + (this.options.$selector.eq(1).val());
          selector = this.options.$selector.eq(2);
      }
    }
    if (this.options.type === 'radio') {
      switch (optionIndex) {
        case 0:
          key = 'root';
          selector = this.options.$selector.filter('[data-option-index=0]').filter(':checked');
          break;
        case 1:
          key = this.options.$selector.filter('[data-option-index=0]').filter(':checked').val();
          selector = this.options.$selector.filter('[data-option-index=1]').filter(':checked');
          break;
        case 2:
          option1 = this.options.$selector.filter('[data-option-index=0]').filter(':checked').val();
          option2 = this.options.$selector.filter('[data-option-index=1]').filter(':checked').val();
          key = option1 + " / " + option2;
          selector = this.options.$selector.filter('[data-option-index=2]').filter(':checked');
      }
    }
    return {
      key: key,
      selector: selector
    };
  };

  LinkedOptions.prototype._updateOptions = function(optionIndex, optionsMap) {
    var $nextOption, $option, $selector, $selectorOptions, availableOptions, initialValue, j, key, l, len, len1, nextSelector, option, ref, selector, updateSelected;
    nextSelector = optionIndex + 1;
    updateSelected = false;
    ref = this._getCurrent(optionIndex), key = ref.key, selector = ref.selector;
    availableOptions = optionsMap[key] || [];
    if (this.options.type === 'select') {
      $selector = this.options.$productForm.find(selector);
      initialValue = $selector.val();
      $selectorOptions = $selector.find('option');
      for (j = 0, len = $selectorOptions.length; j < len; j++) {
        option = $selectorOptions[j];
        $option = $(option);
        if (availableOptions.indexOf(option.value) === -1) {
          if (option.selected) {
            updateSelected = true;
          }
          $option.prop('disabled', true).prop('selected', false);
        } else {
          $option.prop('disabled', false);
        }
      }
      if (availableOptions.indexOf(initialValue) !== -1) {
        $selector.val(initialValue);
      }
      if (updateSelected) {
        $selectorOptions.filter(':not(:disabled)').eq(0).prop('selected', true);
      }
    }
    if (this.options.type === 'radio') {
      $selector = this.options.$selector.filter("[data-option-index=" + optionIndex + "]");
      for (l = 0, len1 = $selector.length; l < len1; l++) {
        option = $selector[l];
        $option = $(option);
        if (availableOptions.indexOf(option.value) === -1) {
          if (option.checked) {
            updateSelected = true;
          }
          $option.prop('disabled', true).prop('checked', false);
        } else {
          $option.prop('disabled', false);
        }
      }
      if (updateSelected) {
        $selector.filter(':not(:disabled)').eq(0).attr('checked', true).trigger('click');
      }
    }
    $selector.trigger('change');
    $nextOption = this.options.$selector.filter("[data-option-index=" + nextSelector + "]");
    if ($nextOption.length !== 0) {
      return this._updateOptions(nextSelector, optionsMap);
    }
  };

  LinkedOptions.prototype._mapVariants = function(product) {
    var j, key, len, optionsMap, ref, variant;
    optionsMap = [];
    optionsMap['root'] = [];
    ref = product.variants;
    for (j = 0, len = ref.length; j < len; j++) {
      variant = ref[j];
      if (variant.available) {
        optionsMap['root'].push(variant.option1);
        optionsMap['root'] = window.ThemeUtils.unique(optionsMap['root']);
        if (product.options.length > 1) {
          key = variant.option1;
          optionsMap[key] = optionsMap[key] || [];
          optionsMap[key].push(variant.option2);
          optionsMap[key] = window.ThemeUtils.unique(optionsMap[key]);
        }
        if (product.options.length > 2) {
          key = variant.option1 + " / " + variant.option2;
          optionsMap[key] = optionsMap[key] || [];
          optionsMap[key].push(variant.option3);
          optionsMap[key] = window.ThemeUtils.unique(optionsMap[key]);
        }
      }
    }
    this._updateOptions(0, optionsMap);
    return this.options.$selector.on('change', (function(_this) {
      return function(event) {
        var index, nextSelector;
        index = parseInt($(event.currentTarget).attr('data-option-index'), 10);
        nextSelector = index + 1;
        return _this._updateOptions(nextSelector, optionsMap);
      };
    })(this));
  };

  LinkedOptions.prototype.prepareRemove = function() {
    return this.options.$selector.off('change');
  };

  return LinkedOptions;

})();

window.VariantHelper = (function() {
  function VariantHelper(options) {
    var defaultOptions, isShopify;
    defaultOptions = {
      $addToCartButton: null,
      $priceFields: null,
      $productForm: null,
      $productThumbnails: null,
      $selector: null,
      type: 'select',
      productJSON: null,
      productSettings: null
    };
    this.options = window.ThemeUtils.extend(defaultOptions, options);
    this.$body = $(document.body);
    this.linkedOptions = null;
    this.enableHistory = false;
    this.$masterSelect = this.options.$productForm.find("#product-select-" + this.options.formID);
    isShopify = window.Shopify && window.Shopify.preview_host;
    if (window.history && window.history.replaceState && this.options.productSettings.enableHistory && !isShopify) {
      this.enableHistory = true;
    }
    this._init();
    this._bindEvents();
  }

  VariantHelper.prototype._init = function() {
    var j, len, ref, select;
    if (this.options.type === 'select') {
      ref = this.options.$selector;
      for (j = 0, len = ref.length; j < len; j++) {
        select = ref[j];
        this._setSelectLabel(null, $(select));
      }
    }
    if (this.options.productSettings.linkedOptions) {
      this.linkedOptions = new LinkedOptions(this.options);
    }
    return this._updateCurrency();
  };

  VariantHelper.prototype._bindEvents = function() {
    return this.options.$selector.on('change', (function(_this) {
      return function(event) {
        return _this._variantChange(event);
      };
    })(this));
  };

  VariantHelper.prototype._setSelectLabel = function(event, $target) {
    var selectedOption;
    if (event == null) {
      event = null;
    }
    if ($target == null) {
      $target = false;
    }
    if (!$target) {
      $target = $(event.currentTarget);
    }
    selectedOption = $target.find('option:selected').val();
    return $target.prev('[data-select-text]').find('[data-selected-option]').text(selectedOption);
  };

  VariantHelper.prototype._getCurrentOptions = function() {
    var $inputs, productOptions;
    productOptions = [];
    $inputs = this.options.$selector;
    if (this.options.type === 'radio') {
      $inputs = $inputs.filter(':checked');
    }
    $inputs.each(function(index, element) {
      return productOptions.push($(element).val());
    });
    return productOptions;
  };

  VariantHelper.prototype._getVariantFromOptions = function(productOptions) {
    var foundVariant, isMatch, j, len, ref, variant;
    if (this.options.productJSON.variants == null) {
      return;
    }
    foundVariant = null;
    ref = this.options.productJSON.variants;
    for (j = 0, len = ref.length; j < len; j++) {
      variant = ref[j];
      isMatch = productOptions.every(function(value, index) {
        return variant.options[index] === value;
      });
      if (isMatch) {
        foundVariant = variant;
      }
    }
    return foundVariant;
  };

  VariantHelper.prototype._updateMasterSelect = function(variant) {
    var ref;
    if (variant == null) {
      return;
    }
    if ((ref = this.$masterSelect.find("[data-variant-id=" + variant.id + "]")) != null) {
      ref.prop('selected', true);
    }
    return this.$masterSelect.trigger('change');
  };

  VariantHelper.prototype._updatePrice = function(variant) {
    var $addToCartButton, $priceFields, productSettings;
    $addToCartButton = this.options.$addToCartButton;
    $priceFields = this.options.$priceFields;
    productSettings = this.options.productSettings;
    if (variant != null) {
      if (variant.available) {
        $addToCartButton.val(productSettings.addToCartText).removeClass('disabled').removeAttr('disabled');
      } else {
        $addToCartButton.val(productSettings.soldOutText).addClass('disabled').attr('disabled', 'disabled');
      }
      if (variant.compare_at_price > variant.price) {
        $priceFields.find('.money:first-child').html(Shopify.formatMoney(variant.price, Theme.moneyFormat));
        $priceFields.find('.original').html(Shopify.formatMoney(variant.compare_at_price, Theme.moneyFormat)).removeClass('hidden');
      } else {
        $priceFields.find('.money').html(Shopify.formatMoney(variant.price, Theme.moneyFormat));
        $priceFields.find('.original').addClass('hidden');
      }
    } else {
      $addToCartButton.val(productSettings.unavailableText).addClass('disabled').attr('disabled', 'disabled');
    }
    return this._updateCurrency();
  };

  VariantHelper.prototype._updateImages = function(variant) {
    var imageId, ref;
    imageId = variant != null ? (ref = variant.featured_image) != null ? ref.id : void 0 : void 0;
    if (imageId == null) {
      return;
    }
    return this.options.$productThumbnails.filter("[data-image-id='" + imageId + "']").trigger('click');
  };

  VariantHelper.prototype._updateHistory = function(variant) {
    var newUrl, variantUrl;
    if (!(this.enableHistory && (variant != null))) {
      return;
    }
    newUrl = [window.location.protocol, '//', window.location.host, window.location.pathname, '?variant=', variant.id];
    variantUrl = newUrl.join('');
    return window.history.replaceState({
      path: variantUrl
    }, '', variantUrl);
  };

  VariantHelper.prototype._variantChange = function(event) {
    var productOptions, variant;
    if (this.options.type === 'select') {
      this._setSelectLabel(event);
    }
    productOptions = this._getCurrentOptions();
    variant = this._getVariantFromOptions(productOptions);
    this._updateMasterSelect(variant);
    this._updatePrice(variant);
    this._updateImages(variant);
    return this._updateHistory(variant);
  };

  VariantHelper.prototype._updateCurrency = function() {
    if (Theme.currencySwitcher) {
      return this.$body.trigger('reset-currency');
    }
  };

  VariantHelper.prototype.prepareRemove = function() {
    var ref;
    this.options.$selector.off('change');
    return (ref = this.linkedOptions) != null ? ref.prepareRemove() : void 0;
  };

  return VariantHelper;

})();

window.ProductView = (function(superClass) {
  extend(ProductView, superClass);

  function ProductView() {
    return ProductView.__super__.constructor.apply(this, arguments);
  }

  ProductView.prototype.events = {
    'click .product-thumbnails img': 'updateProductImage',
    'submit .product-form': 'addToCart'
  };

  ProductView.prototype.initialize = function(options) {
    this.variantHelpers = null;
    if (options.bindSection) {
      this.sectionBinding();
    }
    return this.render();
  };

  ProductView.prototype.render = function() {
    var $productJSON, $productSettings;
    this.$slideshow = this.$('[data-slideshow-container]');
    this.$productForm = $('[data-product-form]', this.$el);
    this.formID = this.$productForm.attr('data-product-form');
    this.productForm = "product-form-" + this.formID;
    this.$productThumbnails = $('.product-thumbnails img', this.$el);
    this.$addToCartButton = $('.add-to-cart input', this.$el);
    this.$priceArea = $('.product-price', this.$el);
    this.$productMessage = $('[data-product-message]', this.$el);
    $productJSON = $("[data-product-json-" + this.formID + "]", this.$el);
    $productSettings = $("[data-product-settings-" + this.formID + "]", this.$el);
    if (!$productJSON.length) {
      return;
    }
    this.productJSON = JSON.parse($productJSON.text());
    this.productSettings = JSON.parse($productSettings.text());
    this.$variantDropdowns = $("[data-option-select=" + this.formID + "]", this.$el);
    this.$variantRadio = $("[data-option-input=" + this.formID + "]", this.$el);
    this.options = this.productJSON.options;
    this.variants = this.productJSON.variants;
    if (!this.$slideshow.length) {
      this.noImageURL = $('.product-big-image', this.$el).data('no-image-svg');
      if ($('html').hasClass('no-svg')) {
        this.noImageURL = $('.product-big-image', this.$el).data('no-image-png');
      }
    }
    this.processing = false;
    if (this.productSettings.imageZoom && !this.$slideshow.length) {
      this.zoomView = new ZoomView({
        el: $('.product-big-image', this.$el)
      });
    }
    this.setupVariants();
    return Shopify.onError = (function(_this) {
      return function(XMLHttpRequest) {
        return _this.handleErrors(XMLHttpRequest);
      };
    })(this);
  };

  ProductView.prototype.setupVariants = function() {
    var dropdownSettings, radioSettings, variantHelperDefaults;
    variantHelperDefaults = {
      $addToCartButton: this.$addToCartButton,
      $priceFields: this.$priceArea,
      $productForm: this.$productForm,
      $productThumbnails: this.$productThumbnails,
      formID: this.formID,
      productSettings: this.productSettings,
      productJSON: this.productJSON
    };
    if (this.$variantDropdowns.length) {
      dropdownSettings = {
        $selector: this.$variantDropdowns,
        type: 'select'
      };
      dropdownSettings = window.ThemeUtils.extend(variantHelperDefaults, dropdownSettings);
      this.variantHelpers = new VariantHelper(dropdownSettings);
      this.$variantDropdowns.trigger('change');
    }
    if (this.$variantRadio.length) {
      radioSettings = {
        $selector: this.$variantRadio,
        type: 'radio'
      };
      radioSettings = window.ThemeUtils.extend(variantHelperDefaults, radioSettings);
      this.variantHelpers = new VariantHelper(radioSettings);
      return this.$variantRadio.trigger('change');
    }
  };

  ProductView.prototype.sectionBinding = function() {
    this.$el.on('shopify:section:load', (function(_this) {
      return function(event) {
        if (!$(event.target).hasClass('section-product')) {
          return;
        }
        _this.delegateEvents();
        return _this.render();
      };
    })(this));
    return this.$el.on('shopify:section:unload', (function(_this) {
      return function(event) {
        var ref, ref1, ref2;
        if (!$(event.target).hasClass('section-product')) {
          return;
        }
        _this.undelegateEvents();
        if ((ref = _this.variantHelpers) != null) {
          ref.prepareRemove();
        }
        if ((ref1 = _this.zoomView) != null) {
          ref1.prepareRemove();
        }
        return (ref2 = _this.zoomView) != null ? ref2.remove() : void 0;
      };
    })(this));
  };

  ProductView.prototype.updateProductImage = function(event) {
    var $target;
    this.$productThumbnails.removeClass('active');
    $target = $(event.currentTarget);
    if (!$target.length) {
      return;
    }
    $target.addClass('active');
    $('.product-big-image img', this.$el).attr({
      'src': $target.data('high-res'),
      'srcset': $target.data('high-res'),
      'alt': $target.attr('alt')
    });
    if (this.productSettings.imageZoom) {
      return $('.product-big-image', this.$el).trigger('prepare-zoom');
    }
  };

  ProductView.prototype.addToCart = function(e) {
    var quantity;
    if (this.productSettings.cartRedirect) {
      return;
    }
    e.preventDefault();
    if (this.processing) {
      return;
    }
    this.processing = true;
    if (Modernizr.cssanimations) {
      this.$('.add-to-cart').addClass('loading');
    } else {
      this.$addToCartButton.val(this.productSettings.processingText);
    }
    quantity = this.$('input[name="quantity"]').val();
    if (quantity === '' || quantity === '0') {
      return setTimeout((function(_this) {
        return function() {
          $('input[name="quantity"]', _this.$el).addClass('error');
          _this.$productMessage.removeClass('success').addClass('error').text(_this.productSettings.setQuantityText);
          $('.add-to-cart', _this.$el).removeClass('loading');
          return _this.processing = false;
        };
      })(this), 500);
    } else {
      return Shopify.addItemFromForm(this.productForm, (function(_this) {
        return function(cartItem) {
          return setTimeout(function() {
            var successMessage;
            if (theme.isHome && _this.$('.add-to-cart').hasClass('express')) {
              window.location.href = '/checkout';
            } else {
              Shopify.getCart(function(cart) {
                return $('.cart-link .cart-count').text(cart.item_count);
              });
              successMessage = _this.productSettings.successMessage.replace('** product **', cartItem.title);
              $('input[name="quantity"]', _this.$el).removeClass('error');
              $('.add-to-cart', _this.$el).removeClass('loading');
              _this.$productMessage.removeClass('error').addClass('success').html(successMessage);
              if (!Modernizr.cssanimations) {
                _this.$addToCartButton.val(_this.productSettings.addToCartText);
              }
            }
            return _this.processing = false;
          }, 1000);
        };
      })(this));
    }
  };

  ProductView.prototype.handleErrors = function(errors) {
    var errorDescription, errorMessage, productTitle;
    errorMessage = $.parseJSON(errors.responseText);
    productTitle = this.productJSON.title;
    errorDescription = errorMessage.description;
    if (errorMessage.description.indexOf(productTitle) > -1) {
      errorDescription = errorDescription.replace(productTitle, "<em>" + productTitle + "</em>");
    }
    if (errorMessage.message === 'Cart Error') {
      return setTimeout((function(_this) {
        return function() {
          _this.$('input[name="quantity"]').removeClass('error');
          _this.$productMessage.removeClass('success').addClass('error').html(errorDescription);
          _this.$('.add-to-cart').removeClass('loading added-success').addClass('added-error');
          if (!Modernizr.cssanimations) {
            _this.$addToCartButton.val(_this.productSettings.addToCartText);
          }
          return _this.processing = false;
        };
      })(this), 1000);
    }
  };

  return ProductView;

})(Backbone.View);

window.Instagram = (function(superClass) {
  extend(Instagram, superClass);

  function Instagram() {
    return Instagram.__super__.constructor.apply(this, arguments);
  }

  Instagram.prototype.initialize = function() {
    this.initializedClass = 'instagram-initialized';
    return this._validate();
  };

  Instagram.prototype._validate = function() {
    var accessToken, isInitialized;
    this.photoContainer = $('[data-instagram-photos]', this.$el);
    this.onBoarding = $('[data-instagram-photo-onboarding]', this.$el);
    accessToken = $('[data-instagram-token]', this.$el).attr('data-instagram-token');
    isInitialized = this.$el.hasClass(this.initializedClass);
    if (this.photoContainer.length) {
      return this._getPhotos(accessToken, isInitialized);
    } else {
      return this._toggleOnBoarding();
    }
  };

  Instagram.prototype._toggleOnBoarding = function() {
    return this.$el.removeClass('module-hidden').removeClass(this.initializedClass);
  };

  Instagram.prototype._getPhotos = function(accessToken, isInitialized) {
    var url;
    if (!accessToken.length) {
      return this._hasError(false);
    }
    if (isInitialized) {
      return;
    }
    url = "https://api.instagram.com/v1/users/self/media/recent?access_token=" + accessToken + "&count=6&callback=";
    return $.ajax({
      type: "GET",
      dataType: "jsonp",
      url: url,
      success: (function(_this) {
        return function(response) {
          var image, j, len, photo, photos, ref, scale;
          if (response.meta.code === 200) {
            photos = [];
            ref = response.data;
            for (j = 0, len = ref.length; j < len; j++) {
              photo = ref[j];
              image = photo.images.standard_resolution;
              scale = image.width > image.height ? 'y' : 'x';
              photos.push("<div class=\"instagram-photo\">\n    <a\n        class=\"instagram-link\"\n        target=\"_blank\"\n        href=\"" + photo.link + "\"\n    >\n        <img\n            class=\"\n                instagram-image\n                instagram-image-scale-" + scale + "\n            \"\n            src=\"" + image.url + "\"\n        />\n    </a>\n</div>");
            }
            _this.photoContainer.html(photos.join(''));
            return _this.$el.removeClass('module-hidden').addClass(_this.initializedClass);
          } else {
            return _this._hasError(response);
          }
        };
      })(this),
      error: (function(_this) {
        return function(response) {
          return _this._hasError(response);
        };
      })(this)
    });
  };

  Instagram.prototype._hasError = function(response) {
    this.$el.addClass('module-hidden').removeClass(this.initializedClass);
    this.photoContainer.html();
    if (response) {
      return console.log("Instagram error: " + response.meta.error_message);
    }
  };

  Instagram.prototype.update = function() {
    return this._validate();
  };

  return Instagram;

})(Backbone.View);


/*********************************************************************
*  #### Twitter Post Fetcher v17.0.3 ####
*  Coded by Jason Mayes 2015. A present to all the developers out there.
*  www.jasonmayes.com
*  Please keep this disclaimer with my code if you use it. Thanks. :-)
*  Got feedback or questions, ask here:
*  http://www.jasonmayes.com/projects/twitterApi/
*  Github: https://github.com/jasonmayes/Twitter-Post-Fetcher
*  Updates will be posted to this site.
*********************************************************************/
(function(root,factory){if(typeof define==='function'&&define.amd){define([],factory);}else if(typeof exports==='object'){module.exports=factory();}else{factory();}}(this,function(){var domNode='';var maxTweets=20;var parseLinks=true;var queue=[];var inProgress=false;var printTime=true;var printUser=true;var formatterFunction=null;var supportsClassName=true;var showRts=true;var customCallbackFunction=null;var showInteractionLinks=true;var showImages=false;var useEmoji=false;var targetBlank=true;var lang='en';var permalinks=true;var dataOnly=false;var script=null;var scriptAdded=false;function handleTweets(tweets){if(customCallbackFunction===null){var x=tweets.length;var n=0;var element=document.getElementById(domNode);var html='<ul>';while(n<x){html+='<li>'+tweets[n]+'</li>';n++;}
html+='</ul>';element.innerHTML=html;}else{customCallbackFunction(tweets);}}
function strip(data){return data.replace(/<b[^>]*>(.*?)<\/b>/gi,function(a,s){return s;}).replace(/class="(?!(tco-hidden|tco-display|tco-ellipsis))+.*?"|data-query-source=".*?"|dir=".*?"|rel=".*?"/gi,'');}
function targetLinksToNewWindow(el){var links=el.getElementsByTagName('a');for(var i=links.length-1;i>=0;i--){links[i].setAttribute('target','_blank');}}
function getElementsByClassName(node,classname){var a=[];var regex=new RegExp('(^| )'+classname+'( |$)');var elems=node.getElementsByTagName('*');for(var i=0,j=elems.length;i<j;i++){if(regex.test(elems[i].className)){a.push(elems[i]);}}
return a;}
function extractImageUrl(image_data){if(image_data!==undefined&&image_data.innerHTML.indexOf('data-image')>=0){var data_src=image_data.innerHTML.match(/data-image=\"([A-z0-9]+:\/\/[A-z0-9]+\.[A-z0-9]+\.[A-z0-9]+\/[A-z0-9]+\/[A-z0-9\-]+)/i)[1];return decodeURIComponent(data_src)+'.jpg';}}
var twitterFetcher={fetch:function(config){if(config.maxTweets===undefined){config.maxTweets=20;}
if(config.enableLinks===undefined){config.enableLinks=true;}
if(config.showUser===undefined){config.showUser=true;}
if(config.showTime===undefined){config.showTime=true;}
if(config.dateFunction===undefined){config.dateFunction='default';}
if(config.showRetweet===undefined){config.showRetweet=true;}
if(config.customCallback===undefined){config.customCallback=null;}
if(config.showInteraction===undefined){config.showInteraction=true;}
if(config.showImages===undefined){config.showImages=false;}
if(config.useEmoji===undefined){config.useEmoji=false;}
if(config.linksInNewWindow===undefined){config.linksInNewWindow=true;}
if(config.showPermalinks===undefined){config.showPermalinks=true;}
if(config.dataOnly===undefined){config.dataOnly=false;}
if(inProgress){queue.push(config);}else{inProgress=true;domNode=config.domId;maxTweets=config.maxTweets;parseLinks=config.enableLinks;printUser=config.showUser;printTime=config.showTime;showRts=config.showRetweet;formatterFunction=config.dateFunction;customCallbackFunction=config.customCallback;showInteractionLinks=config.showInteraction;showImages=config.showImages;useEmoji=config.useEmoji;targetBlank=config.linksInNewWindow;permalinks=config.showPermalinks;dataOnly=config.dataOnly;var head=document.getElementsByTagName('head')[0];if(script!==null){head.removeChild(script);}
script=document.createElement('script');script.type='text/javascript';if(config.list!==undefined){script.src='https://syndication.twitter.com/timeline/list?'+'callback=__twttrf.callback&dnt=false&list_slug='+
config.list.listSlug+'&screen_name='+config.list.screenName+'&suppress_response_codes=true&lang='+(config.lang||lang)+'&rnd='+Math.random();}else if(config.profile!==undefined){script.src='https://syndication.twitter.com/timeline/profile?'+'callback=__twttrf.callback&dnt=false'+'&screen_name='+config.profile.screenName+'&suppress_response_codes=true&lang='+(config.lang||lang)+'&rnd='+Math.random();}else if(config.likes!==undefined){script.src='https://syndication.twitter.com/timeline/likes?'+'callback=__twttrf.callback&dnt=false'+'&screen_name='+config.likes.screenName+'&suppress_response_codes=true&lang='+(config.lang||lang)+'&rnd='+Math.random();}else{script.src='https://cdn.syndication.twimg.com/widgets/timelines/'+
config.id+'?&lang='+(config.lang||lang)+'&callback=__twttrf.callback&'+'suppress_response_codes=true&rnd='+Math.random();}
head.appendChild(script);}},callback:function(data){if(data===undefined||data.body===undefined){inProgress=false;if(queue.length>0){twitterFetcher.fetch(queue[0]);queue.splice(0,1);}
return;}
if(!useEmoji){data.body=data.body.replace(/(<img[^c]*class="Emoji[^>]*>)|(<img[^c]*class="u-block[^>]*>)/g,'');}
if(!showImages){data.body=data.body.replace(/(<img[^c]*class="NaturalImage-image[^>]*>|(<img[^c]*class="CroppedImage-image[^>]*>))/g,'');}
if(!printUser){data.body=data.body.replace(/(<img[^c]*class="Avatar"[^>]*>)/g,'');}
var div=document.createElement('div');div.innerHTML=data.body;if(typeof(div.getElementsByClassName)==='undefined'){supportsClassName=false;}
function swapDataSrc(element){var avatarImg=element.getElementsByTagName('img')[0];if(avatarImg && avatarImg.length){avatarImg.src=avatarImg.getAttribute('data-src-2x');}return element;}
var tweets=[];var authors=[];var times=[];var images=[];var rts=[];var tids=[];var permalinksURL=[];var x=0;if(supportsClassName){var tmp=div.getElementsByClassName('timeline-Tweet');while(x<tmp.length){if(tmp[x].getElementsByClassName('timeline-Tweet-retweetCredit').length>0){rts.push(true);}else{rts.push(false);}
if(!rts[x]||rts[x]&&showRts){tweets.push(tmp[x].getElementsByClassName('timeline-Tweet-text')[0]);tids.push(tmp[x].getAttribute('data-tweet-id'));if(printUser){authors.push(swapDataSrc(tmp[x].getElementsByClassName('timeline-Tweet-author')[0]));}
times.push(tmp[x].getElementsByClassName('dt-updated')[0]);permalinksURL.push(tmp[x].getElementsByClassName('timeline-Tweet-timestamp')[0]);if(tmp[x].getElementsByClassName('timeline-Tweet-media')[0]!==undefined){images.push(tmp[x].getElementsByClassName('timeline-Tweet-media')[0]);}else{images.push(undefined);}}
x++;}}else{var tmp=getElementsByClassName(div,'timeline-Tweet');while(x<tmp.length){if(getElementsByClassName(tmp[x],'timeline-Tweet-retweetCredit').length>0){rts.push(true);}else{rts.push(false);}
if(!rts[x]||rts[x]&&showRts){tweets.push(getElementsByClassName(tmp[x],'timeline-Tweet-text')[0]);tids.push(tmp[x].getAttribute('data-tweet-id'));if(printUser){authors.push(swapDataSrc(getElementsByClassName(tmp[x],'timeline-Tweet-author')[0]));}
times.push(getElementsByClassName(tmp[x],'dt-updated')[0]);permalinksURL.push(getElementsByClassName(tmp[x],'timeline-Tweet-timestamp')[0]);if(getElementsByClassName(tmp[x],'timeline-Tweet-media')[0]!==undefined){images.push(getElementsByClassName(tmp[x],'timeline-Tweet-media')[0]);}else{images.push(undefined);}}
x++;}}
if(tweets.length>maxTweets){tweets.splice(maxTweets,(tweets.length-maxTweets));authors.splice(maxTweets,(authors.length-maxTweets));times.splice(maxTweets,(times.length-maxTweets));rts.splice(maxTweets,(rts.length-maxTweets));images.splice(maxTweets,(images.length-maxTweets));permalinksURL.splice(maxTweets,(permalinksURL.length-maxTweets));}
var arrayTweets=[];var x=tweets.length;var n=0;if(dataOnly){while(n<x){arrayTweets.push({tweet:tweets[n].innerHTML,author:authors[n]?authors[n].innerHTML:'Unknown Author',author_data:{profile_url:authors[n]?authors[n].querySelector('[data-scribe="element:user_link"]').href:null,profile_image:authors[n]?authors[n].querySelector('[data-scribe="element:avatar"]').getAttribute('data-src-1x'):null,profile_image_2x:authors[n]?authors[n].querySelector('[data-scribe="element:avatar"]').getAttribute('data-src-2x'):null,screen_name:authors[n]?authors[n].querySelector('[data-scribe="element:screen_name"]').title:null,name:authors[n]?authors[n].querySelector('[data-scribe="element:name"]').title:null},time:times[n].textContent,timestamp:times[n].getAttribute('datetime').replace('+0000','Z').replace(/([\+\-])(\d\d)(\d\d)/,'$1$2:$3'),image:extractImageUrl(images[n]),rt:rts[n],tid:tids[n],permalinkURL:(permalinksURL[n]===undefined)?'':permalinksURL[n].href});n++;}}else{while(n<x){if(typeof(formatterFunction)!=='string'){var datetimeText=times[n].getAttribute('datetime');var newDate=new Date(times[n].getAttribute('datetime').replace(/-/g,'/').replace('T',' ').split('+')[0]);var dateString=formatterFunction(newDate,datetimeText);times[n].setAttribute('aria-label',dateString);if(tweets[n].textContent){if(supportsClassName){times[n].textContent=dateString;}else{var h=document.createElement('p');var t=document.createTextNode(dateString);h.appendChild(t);h.setAttribute('aria-label',dateString);times[n]=h;}}else{times[n].textContent=dateString;}}
var op='';if(parseLinks){if(targetBlank){targetLinksToNewWindow(tweets[n]);if(printUser){targetLinksToNewWindow(authors[n]);}}
if(printUser){op+='<div class="user">'+strip(authors[n].innerHTML)+'</div>';}
op+='<p class="tweet">'+strip(tweets[n].innerHTML)+'</p>';if(printTime){if(permalinks){op+='<p class="timePosted"><a href="'+permalinksURL[n]+'">'+times[n].getAttribute('aria-label')+'</a></p>';}else{op+='<p class="timePosted">'+
times[n].getAttribute('aria-label')+'</p>';}}}else{if(tweets[n].textContent){if(printUser){op+='<p class="user">'+authors[n].textContent+'</p>';}
op+='<p class="tweet">'+tweets[n].textContent+'</p>';if(printTime){op+='<p class="timePosted">'+times[n].textContent+'</p>';}}else{if(printUser){op+='<p class="user">'+authors[n].textContent+'</p>';}
op+='<p class="tweet">'+tweets[n].textContent+'</p>';if(printTime){op+='<p class="timePosted">'+times[n].textContent+'</p>';}}}
if(showInteractionLinks){op+='<p class="interact"><a href="https://twitter.com/intent/'+'tweet?in_reply_to='+tids[n]+'" class="twitter_reply_icon"'+
(targetBlank?' target="_blank">':'>')+'Reply</a><a href="https://twitter.com/intent/retweet?'+'tweet_id='+tids[n]+'" class="twitter_retweet_icon"'+
(targetBlank?' target="_blank">':'>')+'Retweet</a>'+'<a href="https://twitter.com/intent/favorite?tweet_id='+
tids[n]+'" class="twitter_fav_icon"'+
(targetBlank?' target="_blank">':'>')+'Favorite</a></p>';}
if(showImages&&images[n]!==undefined&&extractImageUrl(images[n])!==undefined){op+='<div class="media">'+'<img src="'+extractImageUrl(images[n])+'" alt="Image from tweet" />'+'</div>';}
if(showImages){arrayTweets.push(op);}else if(!showImages&&tweets[n].textContent.length){arrayTweets.push(op);}
n++;}}
handleTweets(arrayTweets);inProgress=false;if(queue.length>0){twitterFetcher.fetch(queue[0]);queue.splice(0,1);}}};window.__twttrf=twitterFetcher;window.twitterFetcher=twitterFetcher;return twitterFetcher;}));

;

Twitter = (function(superClass) {
  extend(Twitter, superClass);

  function Twitter() {
    return Twitter.__super__.constructor.apply(this, arguments);
  }

  Twitter.prototype.initialize = function() {
    this.initializedClass = 'twitter-initialized';
    return this._validate();
  };

  Twitter.prototype._validate = function() {
    var isInitialized, retweets, username;
    this.tweetContainer = $('[data-twitter-tweets]', this.$el);
    username = $('[data-twitter-username]', this.$el).attr('data-twitter-username');
    retweets = $('[data-show-retweets]', this.$el).length;
    isInitialized = this.$el.hasClass(this.initializedClass);
    if (this.tweetContainer.length) {
      if (!isInitialized) {
        return this._fetchTweets(username, retweets);
      }
    } else {
      return this._toggleOnBoarding();
    }
  };

  Twitter.prototype._toggleOnBoarding = function() {
    return this.$el.removeClass('module-hidden').removeClass(this.initializedClass);
  };

  Twitter.prototype._fetchTweets = function(username, retweets) {
    var config;
    config = {
      'profile': {
        'screenName': username
      },
      'maxTweets': 1,
      'enableLinks': true,
      'showUser': true,
      'showTime': true,
      'showRetweet': retweets,
      'customCallback': (function(_this) {
        return function(tweets) {
          return _this.renderTweets(tweets);
        };
      })(this),
      'showInteraction': false,
      'useEmoji': true
    };
    return twitterFetcher.fetch(config);
  };

  Twitter.prototype.renderTweets = function(tweets) {
    var $tweet;
    if (tweets.length) {
      $tweet = $(tweets[0]);
      this.tweetContainer.html($tweet[1].innerHTML);
      return this.$el.removeClass('module-hidden').addClass(this.initializedClass);
    } else {
      this.tweetContainer.html();
      this.$el.addClass('module-hidden').removeClass(this.initializedClass);
      return console.log("No tweets to display. Most probable cause is an incorrectly entered username.");
    }
  };

  Twitter.prototype.update = function($el) {
    this.$el = $el;
    return this._validate();
  };

  return Twitter;

})(Backbone.View);

window.VideoLoader = (function(superClass) {
  extend(VideoLoader, superClass);

  function VideoLoader() {
    return VideoLoader.__super__.constructor.apply(this, arguments);
  }

  VideoLoader.prototype.initialize = function() {
    this.$window = $(window);
    this.videoObject = {};
    this.youTubeVideo = '[data-video-type=youtube]';
    return this.loadYoutubeVideo();
  };

  VideoLoader.prototype.loadYoutubeVideo = function() {
    var $player, autoplay, hasControls, playerId, playerOptions, sectionId, videoId, videoLayout, videoType;
    $player = this.$el.find(this.youTubeVideo);
    sectionId = this.$el.attr('data-section-id');
    playerId = $player.attr('id');
    videoId = $player.attr('data-video-id');
    videoType = $player.attr('data-video-type');
    videoLayout = $player.attr('data-video-layout');
    autoplay = $player.attr('data-video-autoplay');
    this.videoObject = {
      $parent: $("[data-section-id=" + sectionId + "]"),
      $content: $("[data-section-id=" + sectionId + "]").find('[data-section-content]'),
      $player: $player,
      sectionId: sectionId,
      selector: "#" + playerId,
      videoType: videoType,
      videoLayout: videoLayout,
      autoplay: autoplay
    };
    hasControls = this.videoObject.videoLayout === 'background' ? 0 : 1;
    playerOptions = {
      fitToBackground: true,
      videoId: videoId,
      events: {
        'onReady': (function(_this) {
          return function() {
            return _this.onReady();
          };
        })(this)
      },
      playerVars: {
        autohide: 0,
        autoplay: 0,
        branding: 0,
        controls: hasControls,
        modestbranding: 1,
        playsinline: 1,
        showinfo: 0,
        rel: 0,
        origin: window.location.origin,
        wmode: 'transparent'
      }
    };
    return $("#" + playerId).YTPlayer(playerOptions);
  };

  VideoLoader.prototype.onReady = function() {
    this.videoObject.player = this.videoObject.$player.data('ytPlayer').player;
    if (this.videoObject.videoLayout === 'background') {
      this.videoObject.$parent.on('click', (function(_this) {
        return function() {
          return _this.toggleVideo();
        };
      })(this));
    }
    $(window).on("scroll.yt-" + this.videoObject.sectionId, window.ThemeUtils.debounce((function(_this) {
      return function() {
        if (window.ThemeUtils.inViewport(_this.videoObject.$player)) {
          if (_this.videoObject.autoplay === 'true') {
            return _this.playVideo();
          }
        } else {
          return _this.pauseVideo();
        }
      };
    })(this), 100));
    this.$window.on("resize.yt-" + this.videoObject.sectionId, window.ThemeUtils.debounce((function(_this) {
      return function() {
        return _this.centerContent();
      };
    })(this), 10));
    this.videoObject.$parent.fitVids().addClass('video-loaded');
    this.centerContent();
    if (window.ThemeUtils.inViewport(this.videoObject.$player)) {
      if (this.videoObject.autoplay === 'true') {
        return this.playVideo();
      }
    }
  };

  VideoLoader.prototype.centerContent = function() {
    var contentHeight, videoHeight;
    if (this.videoObject.videoLayout !== 'background') {
      return;
    }
    if (window.ThemeUtils.windowWidth() > 720) {
      videoHeight = this.videoObject.$parent.outerHeight(true);
      contentHeight = this.videoObject.$content.outerHeight(true);
      return this.videoObject.$content.css({
        top: (videoHeight - contentHeight) / 2,
        transform: 'translateY(0)'
      });
    } else {
      return this.videoObject.$content.css({
        top: '',
        transform: 'translateY(0)'
      });
    }
  };


  /*
      Remove video from memory and detach listeners
   */

  VideoLoader.prototype.removeVideo = function(sectionId) {
    if (this.videoObject.sectionId == null) {
      return;
    }
    this.$window.off("scroll.yt-" + this.videoObject.sectionId).off("resize.yt-" + this.videoObject.sectionId);
    this.videoObject.$parent.off('click');
    return delete this.videoObject;
  };

  VideoLoader.prototype.toggleVideo = function() {
    if (this.videoObject.player.getPlayerState() === 1) {
      return this.pauseVideo();
    } else {
      return this.playVideo();
    }
  };

  VideoLoader.prototype.playVideo = function(sectionId) {
    var enablePlay;
    if (sectionId == null) {
      sectionId = false;
    }
    enablePlay = true;
    if (sectionId || this.videoObject.videoLayout !== 'background') {
      enablePlay = false;
    }
    if (enablePlay) {
      return this.videoObject.player.playVideo();
    }
  };

  VideoLoader.prototype.pauseVideo = function() {
    var base;
    if (this.videoObject.videoType === 'youtube' && (typeof (base = this.videoObject.player).getPlayerState === "function" ? base.getPlayerState() : void 0) !== 5) {
      return this.videoObject.player.pauseVideo();
    }
  };

  return VideoLoader;

})(Backbone.View);

window.HomeView = (function(superClass) {
  extend(HomeView, superClass);

  function HomeView() {
    return HomeView.__super__.constructor.apply(this, arguments);
  }

  HomeView.prototype.initialize = function() {
    this.sectionBinding();
    this.classHoist();
    return $(document).on('shopify:section:select.home-page', (function(_this) {
      return function() {
        return _this.classHoist();
      };
    })(this)).on('shopify:section:load.home-page', (function(_this) {
      return function() {
        return _this.classHoist();
      };
    })(this)).on('shopify:section:deselect.home-page', (function(_this) {
      return function() {
        return _this.classHoist();
      };
    })(this));
  };

  HomeView.prototype.sectionBinding = function() {
    this.sections = new ThemeEditor();
    this.sections.register('featured-product', this.featuredProduct(this.sections));
    this.sections.register('instagram', this.instagram(this.sections));
    this.sections.register('twitter', this.twitter(this.sections));
    this.sections.register('image-with-text', this.imageWithText(this.sections));
    this.sections.register('image-with-text-overlay', this.imageWithText(this.sections));
    return this.sections.register('full-width-video-with-text', this.videoWithText(this.sections));
  };

  HomeView.prototype.featuredProduct = function(sections) {
    return {
      instances: {},
      init: function(instance) {
        return this.instances[instance.sectionId] = new ProductView({
          el: instance.$container
        });
      },
      onSectionLoad: function(event) {
        var instance;
        instance = sections.getInstance(event);
        if (this.instances[instance.sectionId] == null) {
          return this.init(instance);
        }
      },
      onSectionSelect: function(event) {
        var instance, ref;
        instance = sections.getInstance(event);
        return (ref = this.instances[instance.sectionId]) != null ? ref.setElement(instance.$container) : void 0;
      },
      onSectionUnload: function(event) {
        var instance, ref;
        instance = sections.getInstance(event);
        if ((ref = this.instances[instance.sectionId]) != null) {
          ref.remove();
        }
        return delete this.instances[instance.sectionId];
      }
    };
  };

  HomeView.prototype.imageWithText = function(sections) {
    return {
      instances: {},
      init: function(instance) {
        return this.instances[instance.sectionId] = new ImagesWithText({
          el: instance.$container
        });
      },
      onSectionLoad: function(event) {
        var instance;
        instance = sections.getInstance(event);
        if (this.instances[instance.sectionId] == null) {
          return this.init(instance);
        } else {
          return this.instances[instance.sectionId].centerText(instance.$container);
        }
      },
      onSectionSelect: function(event) {
        return this.onSectionLoad(event);
      },
      onSectionUnload: function(event) {
        var instance;
        instance = sections.getInstance(event);
        this.instances[instance.sectionId].prepareRemove();
        this.instances[instance.sectionId].remove();
        return delete this.instances[instance.sectionId];
      }
    };
  };

  HomeView.prototype.videoWithText = function(sections) {
    return {
      instances: {},
      init: function(instance) {
        this.instances[instance.sectionId] = new VideoLoader({
          el: instance.$container
        });
        return this.instances[instance.sectionId].centerContent();
      },
      onSectionLoad: function(event) {
        var instance, sectionId;
        instance = sections.getInstance(event);
        sectionId = instance.sectionId;
        if (this.instances[sectionId] == null) {
          return this.init(instance);
        }
      },
      onSectionSelect: function(event) {
        var instance;
        instance = sections.getInstance(event);
        return instance.$container.fitVids();
      },
      onSectionDeselect: function(event) {
        var sectionId;
        sectionId = sections.getInstance(event).sectionId;
        return this.instances[sectionId].playVideo(sectionId);
      },
      onSectionUnload: function(event) {
        var sectionId;
        sectionId = sections.getInstance(event).sectionId;
        this.instances[sectionId].removeVideo();
        return delete this.instances[sectionId];
      }
    };
  };

  HomeView.prototype.instagram = function(sections) {
    return {
      instances: {},
      init: function(instance) {
        return this.instances[instance.sectionId] = new Instagram({
          el: instance.$container
        });
      },
      onSectionLoad: function(event) {
        var instance;
        instance = sections.getInstance(event);
        if (this.instances[instance.sectionId] == null) {
          return this.init(instance);
        }
      },
      onSectionSelect: function(event) {
        var instance, ref, ref1;
        instance = sections.getInstance(event);
        if ((ref = this.instances[instance.sectionId]) != null) {
          ref.$el = instance.$container;
        }
        return (ref1 = this.instances[instance.sectionId]) != null ? ref1.update() : void 0;
      },
      onSectionDeselect: function(event) {
        return this.onSectionSelect(event);
      },
      onSectionUnload: function(event) {
        var instance, ref;
        instance = sections.getInstance(event);
        if ((ref = this.instances[instance.sectionId]) != null) {
          ref.remove();
        }
        return delete this.instances[instance.sectionId];
      }
    };
  };

  HomeView.prototype.twitter = function(sections) {
    return {
      instances: {},
      init: function(instance) {
        return this.instances[instance.sectionId] = new Twitter({
          el: instance.$container
        });
      },
      onSectionLoad: function(event) {
        var instance;
        instance = sections.getInstance(event);
        if (this.instances[instance.sectionId] == null) {
          return this.init(instance);
        }
      },
      onSectionDeselect: function(event) {
        var instance, ref, ref1;
        instance = sections.getInstance(event);
        if ((ref = this.instances[instance.sectionId]) != null) {
          ref.$el = instance.$container;
        }
        return (ref1 = this.instances[instance.sectionId]) != null ? ref1.update() : void 0;
      },
      onSectionUnload: function(event) {
        var instance, ref;
        instance = sections.getInstance(event);
        if ((ref = this.instances[instance.sectionId]) != null) {
          ref.remove();
        }
        return delete this.instances[instance.sectionId];
      }
    };
  };

  HomeView.prototype.getStyle = function($el) {
    var styleSetting;
    styleSetting = $el.attr('class').match(/(default|contrast|accent)-style/);
    if (styleSetting != null) {
      return styleSetting[0];
    } else {
      return false;
    }
  };

  HomeView.prototype.classHoist = function() {
    $('.module-container').each((function(_this) {
      return function(index, section) {
        var $parent, $section, parentStyle, sectionStyle;
        $section = $(section);
        $parent = $section.parent();
        sectionStyle = _this.getStyle($section);
        parentStyle = _this.getStyle($parent);
        if (!sectionStyle) {
          return;
        }
        if (parentStyle) {
          $parent.removeClass(parentStyle);
        }
        return $parent.addClass(sectionStyle);
      };
    })(this));
    return true;
  };

  HomeView.prototype.render = function() {};

  return HomeView;

})(Backbone.View);

window.CollectionView = (function(superClass) {
  extend(CollectionView, superClass);

  function CollectionView() {
    return CollectionView.__super__.constructor.apply(this, arguments);
  }

  CollectionView.prototype.events = {
    'change .collection-tag-selector select': 'browseByTag'
  };

  CollectionView.prototype.initialize = function() {
    return this.sectionBinding();
  };

  CollectionView.prototype.sectionBinding = function() {
    this.$el.on('shopify:section:load', (function(_this) {
      return function() {
        return _this.delegateEvents();
      };
    })(this));
    return this.$el.on('shopify:section:unload', (function(_this) {
      return function() {
        return _this.undelegateEvents();
      };
    })(this));
  };

  CollectionView.prototype.browseByTag = function(e) {
    var fallback, newTag, select;
    select = $(e.target);
    fallback = select.data('fallback-url');
    newTag = select.find(':selected').attr('name');
    if (newTag === 'reset') {
      return window.location.href = fallback;
    } else {
      return window.location.href = fallback + "/" + newTag;
    }
  };

  CollectionView.prototype.render = function() {};

  return CollectionView;

})(Backbone.View);

window.ListCollectionsView = (function(superClass) {
  extend(ListCollectionsView, superClass);

  function ListCollectionsView() {
    return ListCollectionsView.__super__.constructor.apply(this, arguments);
  }

  ListCollectionsView.prototype.events = {};

  ListCollectionsView.prototype.initialize = function() {
    var collection, collectionDetails, collections, j, len, results;
    if ($('html').hasClass('lt-ie9')) {
      collections = this.$('.collection-list-item');
      results = [];
      for (j = 0, len = collections.length; j < len; j++) {
        collection = collections[j];
        collectionDetails = $(collection).find('.collection-details');
        results.push(this.verticallyAlignText(collectionDetails));
      }
      return results;
    }
  };

  ListCollectionsView.prototype.verticallyAlignText = function(collectionDetails) {
    var textHeight;
    textHeight = collectionDetails.height();
    return collectionDetails.css({
      marginTop: -(textHeight / 2)
    });
  };

  ListCollectionsView.prototype.render = function() {};

  return ListCollectionsView;

})(Backbone.View);

window.ContactView = (function(superClass) {
  extend(ContactView, superClass);

  function ContactView() {
    return ContactView.__super__.constructor.apply(this, arguments);
  }

  ContactView.prototype.events = {
    "submit .contact-form": "spamCheck"
  };

  ContactView.prototype.spamCheck = function(event) {
    if (this.$(event.target).find(".spam-check").val().length > 0) {
      return event.preventDefault();
    }
  };

  return ContactView;

})(Backbone.View);

window.CartView = (function(superClass) {
  extend(CartView, superClass);

  function CartView() {
    return CartView.__super__.constructor.apply(this, arguments);
  }

  CartView.prototype.events = {
    'click .cart-item-decrease': 'updateQuantity',
    'click .cart-item-increase': 'updateQuantity',
    'change .cart-instructions textarea': 'saveSpecialInstructions',
    'click .dismiss': 'closeModal',
    'click .get-rates': 'calculateShipping'
  };

  CartView.prototype.initialize = function() {
    this.sectionBinding();
    return this.render();
  };

  CartView.prototype.render = function() {
    var error;
    this.context = {};
    this.context.cart = null;
    this.context.shipping = null;
    this.$cartStrings = $('[data-cart-strings]');
    this.$shippingCalculator = $('[data-shipping-calculator]');
    if (this.$cartStrings.length) {
      try {
        this.context.cart = JSON.parse($('[data-cart-strings]').text());
      } catch (error1) {
        error = error1;
        console.log('No cart localisations found, unable to continue.');
      }
      if (this.context.cart == null) {
        return;
      }
    }
    if (this.$shippingCalculator.length) {
      try {
        this.context.shipping = JSON.parse($('[data-shipping-calculator-strings]').text());
      } catch (error1) {
        error = error1;
        console.log('No shipping localisations found, unable to continue.');
      }
      if (this.context.shipping == null) {
        return;
      }
      if (this.context.shipping.customerCountry) {
        this.calculateShipping();
      }
      if (this.$('.cart-items').length) {
        this.shippingCalculator();
      }
    }
    this.modalWrapper = this.$('.cart-modal-wrapper');
    this.modalTitle = this.$('.cart-modal h3');
    this.modalMessage = this.$('.cart-modal-message');
    this.modalAction = this.$('.cart-modal-action');
    return Shopify.onError = (function(_this) {
      return function(XMLHttpRequest) {
        return _this.handleErrors(XMLHttpRequest);
      };
    })(this);
  };

  CartView.prototype.sectionBinding = function() {
    this.$el.on('shopify:section:load', (function(_this) {
      return function() {
        _this.delegateEvents();
        return _this.initialize();
      };
    })(this));
    return this.$el.on('shopify:section:unload', (function(_this) {
      return function() {
        return _this.undelegateEvents();
      };
    })(this));
  };

  CartView.prototype.saveSpecialInstructions = function() {
    var newNote;
    newNote = $('.cart-instructions textarea').val();
    return Shopify.updateCartNote(newNote, function(cart) {});
  };

  CartView.prototype.updateQuantity = function(e) {
    var newQuantity, oldQuantity, productPrice, productQuantity, productRow, productTitle, variant;
    productRow = $(e.target).parents('tr');
    productTitle = productRow.find('.cart-title').text();
    productPrice = productRow.find('td.cart-item-total .money');
    productQuantity = productRow.find('.cart-item-quantity-display');
    variant = productRow.data('variant');
    oldQuantity = parseInt(productQuantity.val(), 10);
    if ($(e.target).hasClass('cart-item-increase')) {
      newQuantity = oldQuantity + 1;
    } else {
      newQuantity = oldQuantity <= 1 ? 0 : oldQuantity - 1;
    }
    productRow.find('.cart-item-quantity-display').val(newQuantity);
    return Shopify.changeItem(variant, newQuantity, (function(_this) {
      return function(cart) {
        var action, cartItem, cartItemQuantity, item, message, title;
        if (newQuantity === 0) {
          return location.reload();
        } else {
          cartItem = cart.items.filter(function(item) {
            return item.id === variant;
          });
          item = cartItem[0];
          if (item) {
            cartItemQuantity = item.quantity;
            if (cartItemQuantity !== newQuantity) {
              newQuantity = cartItemQuantity;
              title = _this.context.cart.notAvailableText;
              message = _this.context.cart.stockLevelText.replace('** stock_count **', cartItemQuantity);
              action = "<span class='button dismiss'>" + _this.context.cart.okayText + "</span>";
              productRow.find('.cart-item-quantity-display').val(newQuantity);
              return _this.openModal(title, message, action);
            }
          }
        }
      };
    })(this));
  };

  CartView.prototype.shippingCalculator = function() {
    var selectableOptions;
    Shopify.Cart.ShippingCalculator.show({
      submitButton: this.context.shipping.submitButton,
      submitButtonDisabled: this.context.shipping.submitButtonProcessing,
      customerIsLoggedIn: this.context.shipping.customerCountry,
      moneyFormat: Theme.moneyFormat
    });
    selectableOptions = this.$('.cart-shipping-calculator select');
    setTimeout((function(_this) {
      return function() {
        var j, len, results, select;
        results = [];
        for (j = 0, len = selectableOptions.length; j < len; j++) {
          select = selectableOptions[j];
          results.push(_this.updateShippingLabel(select));
        }
        return results;
      };
    })(this), 500);
    return this.$('.cart-shipping-calculator select').change((function(_this) {
      return function(e) {
        var j, len, results, select;
        results = [];
        for (j = 0, len = selectableOptions.length; j < len; j++) {
          select = selectableOptions[j];
          results.push(_this.updateShippingLabel(select));
        }
        return results;
      };
    })(this));
  };

  CartView.prototype.calculateShipping = function() {
    var shippingAddress;
    $('.get-rates').val(this.context.shipping.submitButtonProcessing);
    shippingAddress = {};
    shippingAddress.zip = $('.address-zip').val() || '';
    shippingAddress.country = $('.address-country').val() || '';
    shippingAddress.province = $('.address-province').val() || '';
    return Shopify.getCartShippingRatesForDestination(shippingAddress, (function(_this) {
      return function() {
        var address, firstRate, j, len, price, rate, rateValues, ratesFeedback, responseText, shippingCalculatorResponse;
        address = shippingAddress.zip + ", " + shippingAddress.province + ", " + shippingAddress.country;
        if (!shippingAddress.province.length) {
          address = shippingAddress.zip + ", " + shippingAddress.country;
        }
        if (!shippingAddress.zip.length) {
          address = shippingAddress.province + ", " + shippingAddress.country;
        }
        if (!(shippingAddress.province.length && shippingAddress.zip.length)) {
          address = shippingAddress.country;
        }
        shippingCalculatorResponse = $('.cart-shipping-calculator-response');
        shippingCalculatorResponse.empty().append("<p class='shipping-calculator-response message'/><ul class='shipping-rates'/>");
        ratesFeedback = $('.shipping-calculator-response');
        if (rates.length > 1) {
          firstRate = Shopify.Cart.ShippingCalculator.formatRate(rates[0].price);
          responseText = _this.context.shipping.multiRates.replace('** address **', address).replace('** number_of_rates **', rates.length).replace('** rate **', "<span class='money'>" + firstRate + "</span>");
          ratesFeedback.html(responseText);
        } else if (rates.length === 1) {
          responseText = _this.context.shipping.oneRate.replace('** address **', address);
          ratesFeedback.html(responseText);
        } else {
          ratesFeedback.html(_this.context.shipping.noRates);
        }
        for (j = 0, len = rates.length; j < len; j++) {
          rate = rates[j];
          price = Shopify.Cart.ShippingCalculator.formatRate(rate.price);
          rateValues = _this.context.shipping.rateValues.replace('** rate_title **', rate.name).replace('** rate **', "<span class='money'>" + price + "</span>");
          $('.shipping-rates').append("<li>" + rateValues + "</li>");
        }
        return $('.get-rates').val(_this.context.shipping.submitButton);
      };
    })(this));
  };

  CartView.prototype.updateShippingLabel = function(select) {
    var selectedOption;
    if (select) {
      select = $(select);
      selectedOption = select.find('option:selected').val();
      if (!selectedOption) {
        selectedOption = select.prev('.selected-text').data('default');
      }
      select.prev('.selected-text').text(selectedOption);
      return setTimeout((function(_this) {
        return function() {
          if (select.attr('name') === 'address[country]') {
            return _this.updateShippingLabel(_this.$('#address_province'));
          }
        };
      })(this), 500);
    }
  };

  CartView.prototype.openModal = function(title, message, action) {
    this.modalTitle.text(title);
    this.modalMessage.text(message);
    this.modalAction.html(action);
    return this.modalWrapper.addClass('active');
  };

  CartView.prototype.closeModal = function() {
    return this.modalWrapper.removeClass('active');
  };

  CartView.prototype.handleErrors = function(errors) {
    var errorMessage;
    errorMessage = $.parseJSON(errors.responseText);
    if (!errorMessage.zip) {
      return;
    }
    errorMessage = this.context.shipping.errorMessage.replace('** error_message **', errorMessage.zip);
    return $('.cart-shipping-calculator-response').html("<p>" + errorMessage + "</p>");
  };

  return CartView;

})(Backbone.View);

window.ArticleListView = (function(superClass) {
  extend(ArticleListView, superClass);

  function ArticleListView() {
    return ArticleListView.__super__.constructor.apply(this, arguments);
  }

  ArticleListView.prototype.initialize = function() {
    var highlight, j, len, ref;
    this.setFeaturedImage(true);
    this.artDirection();
    this.wrapAllNodes();
    ref = this.$('.highlight');
    for (j = 0, len = ref.length; j < len; j++) {
      highlight = ref[j];
      this.fixOverlappingElements($(highlight));
    }
    return $(window).resize((function(_this) {
      return function() {
        var l, len1, ref1, results;
        _this.setFeaturedImage();
        if (window.innerWidth > 1020) {
          ref1 = _this.$('.highlight');
          results = [];
          for (l = 0, len1 = ref1.length; l < len1; l++) {
            highlight = ref1[l];
            results.push(_this.fixOverlappingElements($(highlight)));
          }
          return results;
        }
      };
    })(this));
  };

  ArticleListView.prototype.wrapAllNodes = function() {
    var childNodes, j, len, node, results;
    childNodes = this.$('.rte')[0].childNodes;
    results = [];
    for (j = 0, len = childNodes.length; j < len; j++) {
      node = childNodes[j];
      if (node.nodeType === 3 && node.textContent.replace(/^\s+|\s+$/g, "")) {
        results.push($(node).replaceWith("<p>" + node.textContent + "</p>"));
      } else {
        results.push(void 0);
      }
    }
    return results;
  };

  ArticleListView.prototype.fixOverlappingElements = function(highlight) {
    if (this.$('.post-meta').overlaps(highlight).length) {
      highlight.addClass('overlapping');
    }
    return highlight.addClass('processed');
  };

  ArticleListView.prototype.setFeaturedImage = function(load) {
    var contentWidth, featuredImage, windowWidth;
    featuredImage = this.$('.featured-image');
    if (featuredImage.length) {
      if (featuredImage.hasClass('full-bleed-featured-image')) {
        windowWidth = $(window).width();
        contentWidth = this.$el.outerWidth(true);
        featuredImage.css({
          width: windowWidth,
          marginLeft: -1 * (windowWidth - contentWidth) / 2
        });
      }
      if (load) {
        return featuredImage.addClass('processed');
      }
    }
  };

  ArticleListView.prototype.artDirection = function() {
    var images;
    images = this.$('.post-content').find('img');
    return images.imagesLoaded((function(_this) {
      return function() {
        var direction, image, imageAlt, imageParent, imageWidth, j, len, marginLeft, marginRight, results;
        results = [];
        for (j = 0, len = images.length; j < len; j++) {
          image = images[j];
          image = $(image);
          if (!image.hasClass('post-image')) {
            if (image.parent().hasClass('post-content')) {
              image.wrap('<div />');
            }
            imageParent = image.parent();
            if (image.css('float') !== 'none') {
              direction = image.css('float');
              imageParent.addClass("highlight highlight-" + direction);
              _this.fixOverlappingElements(imageParent);
            }
            imageWidth = image.width();
            imageAlt = image.attr('alt');
            if (imageAlt && imageAlt.length && imageParent.not('img')) {
              marginLeft = image.css('margin-left');
              marginRight = image.css('margin-right');
              results.push(imageParent.append("<div style='max-width: " + imageWidth + "px; margin-left: " + marginLeft + "; margin-right: " + marginRight + ";' class='photo-caption meta'>" + imageAlt + "</div>"));
            } else {
              results.push(void 0);
            }
          } else {
            results.push(void 0);
          }
        }
        return results;
      };
    })(this));
  };

  return ArticleListView;

})(Backbone.View);

window.BlogView = (function(superClass) {
  extend(BlogView, superClass);

  function BlogView() {
    return BlogView.__super__.constructor.apply(this, arguments);
  }

  BlogView.prototype.initialize = function() {
    this.listViews = [];
    this.sectionBinding();
    return this.render();
  };

  BlogView.prototype.render = function() {
    var $articleListItem, j, len, listItem, results;
    $articleListItem = this.$('[data-blog-list-item]');
    if ($articleListItem.length === 0) {
      return;
    }
    results = [];
    for (j = 0, len = $articleListItem.length; j < len; j++) {
      listItem = $articleListItem[j];
      results.push(this.listViews.push(new ArticleListView({
        el: listItem
      })));
    }
    return results;
  };

  BlogView.prototype.sectionBinding = function() {
    this.$el.on('shopify:section:load', (function(_this) {
      return function() {
        return _this.render();
      };
    })(this));
    return this.$el.on('shopify:section:unload', (function(_this) {
      return function() {
        var j, len, listView, ref, results;
        ref = _this.listViews;
        results = [];
        for (j = 0, len = ref.length; j < len; j++) {
          listView = ref[j];
          results.push(listView.remove());
        }
        return results;
      };
    })(this));
  };

  return BlogView;

})(Backbone.View);

window.AddressesView = (function(superClass) {
  extend(AddressesView, superClass);

  function AddressesView() {
    return AddressesView.__super__.constructor.apply(this, arguments);
  }

  AddressesView.prototype.events = {
    'click .delete-address': 'deleteAddress',
    'click .edit-address': 'editAddress',
    'click .cancel-edit': 'cancelEditing',
    'click .toggle-new-address': 'toggleNewAddress',
    'change .select-wrapper select': 'updateSelectedText'
  };

  AddressesView.prototype.initialize = function() {
    return this.prepareAddresses();
  };

  AddressesView.prototype.prepareAddresses = function() {
    var address, addressID, addresses, j, l, len, len1, results, select, selectableOptions;
    new Shopify.CountryProvinceSelector('address-country', 'address-province', {
      hideElement: 'address-province-container'
    });
    addresses = this.$('.customer-address');
    if (addresses.length) {
      for (j = 0, len = addresses.length; j < len; j++) {
        address = addresses[j];
        addressID = $(address).data('address-id');
        new Shopify.CountryProvinceSelector("address-country-" + addressID, "address-province-" + addressID, {
          hideElement: "address-province-container-" + addressID
        });
      }
    }
    selectableOptions = this.$('.select-wrapper select');
    results = [];
    for (l = 0, len1 = selectableOptions.length; l < len1; l++) {
      select = selectableOptions[l];
      results.push(this.updateSelectedText(null, select));
    }
    return results;
  };

  AddressesView.prototype.updateSelectedText = function(e, select) {
    var addressID, selectedValue;
    select = e ? $(e.target) : $(select);
    selectedValue = select.find('option:selected').text();
    if (selectedValue !== '') {
      select.prev('.selected-text').text(selectedValue);
    }
    if (select.attr('name') === 'address[country]') {
      addressID = $(select).attr('id').split('address-country-')[1];
      addressID = addressID ? "#address-province-" + addressID : '.new-address-province';
      return this.updateSelectedText(null, $(addressID));
    }
  };

  AddressesView.prototype.deleteAddress = function(e) {
    var addressID;
    addressID = $(e.target).parents('[data-address-id]').data('address-id');
    return Shopify.CustomerAddress.destroy(addressID);
  };

  AddressesView.prototype.editAddress = function(e) {
    var addressID;
    addressID = $(e.target).parents('[data-address-id]').data('address-id');
    $(".customer-address[data-address-id='" + addressID + "']").addClass('editing');
    return $(".customer-address-edit-form[data-address-id='" + addressID + "']").addClass('show');
  };

  AddressesView.prototype.cancelEditing = function(e) {
    var addressID;
    addressID = $(e.target).parents('[data-address-id]').data('address-id');
    $(".customer-address[data-address-id='" + addressID + "']").removeClass('editing');
    return $(".customer-address-edit-form[data-address-id='" + addressID + "']").removeClass('show');
  };

  AddressesView.prototype.toggleNewAddress = function() {
    this.$('.add-new-address').toggle();
    return this.$('.customer-new-address').toggleClass('show');
  };

  AddressesView.prototype.render = function() {};

  return AddressesView;

})(Backbone.View);

window.AccountView = (function(superClass) {
  extend(AccountView, superClass);

  function AccountView() {
    return AccountView.__super__.constructor.apply(this, arguments);
  }

  AccountView.prototype.events = {
    'click .toggle-forgetfulness span': 'recoverPassword'
  };

  AccountView.prototype.initialize = function() {
    if ($(document.body).hasClass('template-customers-addresses')) {
      this.addressesView = new AddressesView({
        el: $('.main-content')
      });
    }
    if ($(document.body).hasClass('template-customers-login')) {
      this.checkForReset();
    }
    if (window.location.hash === '#recover') {
      this.recoverPassword();
    }
    this.mobilifyTables();
    return $(window).resize((function(_this) {
      return function() {
        return _this.mobilifyTables();
      };
    })(this));
  };

  AccountView.prototype.recoverPassword = function() {
    this.$('.recover-password').toggle();
    return this.$('.customer-login').toggle();
  };

  AccountView.prototype.checkForReset = function() {
    if ($('.reset-check').data('successful-reset') === true) {
      return $('.successful-reset').show();
    }
  };

  AccountView.prototype.mobilifyTables = function() {
    return this.$('.orders').mobileTable();
  };

  AccountView.prototype.render = function() {};

  return AccountView;

})(Backbone.View);

window.RTEView = (function(superClass) {
  extend(RTEView, superClass);

  function RTEView() {
    return RTEView.__super__.constructor.apply(this, arguments);
  }

  RTEView.prototype.events = {
    'click .tabs li': 'switchTabs',
    'change .select-wrapper select': 'updateOption'
  };

  RTEView.prototype.initialize = function() {
    var j, len, select, selects;
    this.setupTabs();
    selects = this.$el.find('select');
    for (j = 0, len = selects.length; j < len; j++) {
      select = selects[j];
      if (!$(select).parent('.select-wrapper').length) {
        $(select).wrap('<div class="select-wrapper" />').parent().prepend('<span class="selected-text"></span>');
      }
      this.updateOption(null, select);
    }
    this.$el.fitVids();
    this.mobilifyTables();
    return $(window).resize((function(_this) {
      return function() {
        return _this.mobilifyTables();
      };
    })(this));
  };

  RTEView.prototype.switchTabs = function(e) {
    var position, tab;
    e.preventDefault();
    tab = $(e.currentTarget);
    position = tab.index();
    this.tabs.removeClass('active');
    this.tabsContent.removeClass('active');
    tab.addClass('active');
    return this.tabsContent.eq(position).addClass('active');
  };

  RTEView.prototype.setupTabs = function() {
    this.tabs = this.$('.tabs > li');
    this.tabsContent = this.$('.tabs-content > li');
    this.tabs.first().addClass('active');
    return this.tabsContent.first().addClass('active');
  };

  RTEView.prototype.updateOption = function(e, selector) {
    var newOption, select;
    select = e ? $(e.target) : $(selector);
    newOption = select.find('option:selected').text();
    return select.siblings('.selected-text').text(newOption);
  };

  RTEView.prototype.mobilifyTables = function() {
    return this.$el.find('table').mobileTable();
  };

  return RTEView;

})(Backbone.View);

window.NotFoundView = (function(superClass) {
  extend(NotFoundView, superClass);

  function NotFoundView() {
    return NotFoundView.__super__.constructor.apply(this, arguments);
  }

  NotFoundView.prototype.events = {};

  NotFoundView.prototype.initialize = function() {};

  NotFoundView.prototype.render = function() {};

  return NotFoundView;

})(Backbone.View);

window.CurrencyView = (function(superClass) {
  extend(CurrencyView, superClass);

  function CurrencyView() {
    return CurrencyView.__super__.constructor.apply(this, arguments);
  }

  CurrencyView.prototype.events = {
    'change [name=currencies]': 'convertAll',
    'switch-currency': 'switchCurrency',
    'reset-currency': 'resetCurrency'
  };

  CurrencyView.prototype.initialize = function() {
    this.sectionBinding();
    return this.render();
  };

  CurrencyView.prototype.sectionBinding = function() {
    this.$el.on('shopify:section:load', (function(_this) {
      return function() {
        _this.delegateEvents();
        return _this.render();
      };
    })(this));
    return this.$el.on('shopify:section:unload', (function(_this) {
      return function() {
        return _this.undelegateEvents();
      };
    })(this));
  };

  CurrencyView.prototype.render = function() {
    var doubleMoney, j, l, len, len1, money, ref, ref1;
    Currency.format = Theme.currencySwitcherFormat;
    Currency.money_with_currency_format[Theme.currency] = Theme.moneyFormatCurrency;
    Currency.money_format[Theme.currency] = Theme.moneyFormat;
    this.defaultCurrency = Theme.defaultCurrency || Theme.currency;
    this.cookieCurrency = Currency.cookie.read();
    if (this.cookieCurrency) {
      this.$("[name=currencies]").val(this.cookieCurrency);
    }
    ref = this.$('span.money span.money');
    for (j = 0, len = ref.length; j < len; j++) {
      doubleMoney = ref[j];
      $(doubleMoney).parents('span.money').removeClass('money');
    }
    ref1 = this.$('span.money');
    for (l = 0, len1 = ref1.length; l < len1; l++) {
      money = ref1[l];
      $(money).attr("data-currency-" + Theme.currency, $(money).html());
    }
    this.switchCurrency();
    return this.$('.selected-currency').text(Currency.currentCurrency);
  };

  CurrencyView.prototype.resetCurrency = function() {
    var attribute, j, l, len, len1, money, ref, ref1;
    ref = this.$('span.money');
    for (j = 0, len = ref.length; j < len; j++) {
      money = ref[j];
      ref1 = $(money)[0].attributes;
      for (l = 0, len1 = ref1.length; l < len1; l++) {
        attribute = ref1[l];
        if (attribute.name.indexOf('data-') > -1) {
          $(money).attr(attribute.name, '');
        }
      }
    }
    return this.switchCurrency();
  };

  CurrencyView.prototype.switchCurrency = function() {
    if (this.cookieCurrency === null) {
      if (Theme.currency === !this.defaultCurrency) {
        return Currency.convertAll(Theme.currency, this.defaultCurrency);
      } else {
        return Currency.currentCurrency = this.defaultCurrency;
      }
    } else if (this.$('[name=currencies]').size() && this.$('[name=currencies] option[value=' + this.cookieCurrency + ']').size() === 0) {
      Currency.currentCurrency = Theme.currency;
      return Currency.cookie.write(Theme.currency);
    } else if (this.cookieCurrency === Theme.currency) {
      return Currency.currentCurrency = Theme.currency;
    } else {
      return Currency.convertAll(Theme.currency, this.cookieCurrency);
    }
  };

  CurrencyView.prototype.convertAll = function(e, variant, selector) {
    var newCurrency;
    newCurrency = $(e.target).val();
    Currency.convertAll(Currency.currentCurrency, newCurrency);
    this.$('.selected-currency').text(Currency.currentCurrency);
    return this.cookieCurrency = newCurrency;
  };

  return CurrencyView;

})(Backbone.View);

window.GiftCardView = (function(superClass) {
  extend(GiftCardView, superClass);

  function GiftCardView() {
    return GiftCardView.__super__.constructor.apply(this, arguments);
  }

  GiftCardView.prototype.initialize = function() {
    return this.addQrCode();
  };

  GiftCardView.prototype.addQrCode = function() {
    var qrWrapper;
    qrWrapper = $('[data-qr-code]');
    return new QRCode(qrWrapper[0], {
      text: qrWrapper.data('qr-code'),
      width: 120,
      height: 120
    });
  };

  return GiftCardView;

})(Backbone.View);

window.ThemeEditor = (function(superClass) {
  extend(ThemeEditor, superClass);

  function ThemeEditor() {
    return ThemeEditor.__super__.constructor.apply(this, arguments);
  }

  ThemeEditor.prototype.initialize = function() {
    this.instanceHandlers = {};
    this.instances = {};
    return $(document).on('shopify:section:load', (function(_this) {
      return function(event) {
        return _this._onSectionLoad(event);
      };
    })(this)).on('shopify:section:unload', (function(_this) {
      return function(event) {
        return _this._onSectionUnload(event);
      };
    })(this)).on('shopify:section:select', (function(_this) {
      return function(event) {
        return _this._onSectionSelect(event);
      };
    })(this)).on('shopify:section:deselect', (function(_this) {
      return function(event) {
        return _this._onSectionDeselect(event);
      };
    })(this)).on('shopify:block:select', (function(_this) {
      return function(event) {
        return _this._onBlockSelect(event);
      };
    })(this)).on('shopify:block:deselect', (function(_this) {
      return function(event) {
        return _this._onBlockDeselect(event);
      };
    })(this));
  };

  ThemeEditor.prototype._findInstance = function(event) {
    var $container, instance;
    instance = this.instances[event.originalEvent.detail.sectionId];
    if (instance != null) {
      return instance;
    } else {
      $container = $('[data-section-id]', event.target);
      return this._createInstance($container);
    }
  };

  ThemeEditor.prototype._createInstance = function($container, instanceHandler) {
    var data, el, instance, sectionId, sectionType;
    el = $container.parent().get(0);
    data = this._loadData(el);
    sectionType = $container.attr('data-section-type');
    sectionId = $container.attr('data-section-id');
    if (sectionType == null) {
      return;
    }
    instanceHandler = instanceHandler || this.instanceHandlers[sectionType];
    instance = {
      el: el,
      data: data,
      instanceHandler: instanceHandler,
      $container: $container,
      sectionId: sectionId
    };
    this.instances[sectionId] = instance;
    return instance;
  };

  ThemeEditor.prototype._loadData = function(el) {
    var data, dataEl, error;
    dataEl = el.querySelector('[data-section-data]');
    if (!dataEl) {
      return {};
    }
    data = dataEl.getAttribute('data-section-data') || dataEl.innerHTML;
    try {
      return JSON.parse(data);
    } catch (error1) {
      error = error1;
      console.warn("Sections: invalid section data found. " + error.message);
      return {};
    }
  };


  /*
      Action: A section has been added or re-rendered.
      Expected: Re-execute any JavaScript needed for the section to work and
          display properly (as if the page had just been loaded).
   */

  ThemeEditor.prototype._onSectionLoad = function(event) {
    var $container, ref, ref1;
    $container = $('[data-section-id]', event.target);
    if (!$container.length) {
      return;
    }
    return (ref = this._createInstance($container)) != null ? (ref1 = ref.instanceHandler) != null ? typeof ref1.onSectionLoad === "function" ? ref1.onSectionLoad(event) : void 0 : void 0 : void 0;
  };


  /*
      Action: A section has been deleted or is being re-rendered.
      Expected: Clean up any event listeners, variables, etc., so that
          nothing breaks when the page is interacted with and no memory leaks occur.
   */

  ThemeEditor.prototype._onSectionUnload = function(event) {
    var instance, ref;
    instance = this._findInstance(event);
    if (instance != null) {
      if ((ref = instance.instanceHandler) != null) {
        if (typeof ref.onSectionUnload === "function") {
          ref.onSectionUnload(event);
        }
      }
    }
    if (instance) {
      return delete this.instances[instance.sectionId];
    }
  };


  /*
      Action: User has selected the section in the sidebar.
      Expected: Make sure the section is in view and stays
          in view while selected (scrolling happens automatically).
      Example: Could be used to pause a slideshow
   */

  ThemeEditor.prototype._onSectionSelect = function(event) {
    var ref, ref1;
    return (ref = this._findInstance(event)) != null ? (ref1 = ref.instanceHandler) != null ? typeof ref1.onSectionSelect === "function" ? ref1.onSectionSelect(event) : void 0 : void 0 : void 0;
  };


  /*
      Action: User has deselected the section in the sidebar.
      Expected: (None)
      Example: Could be used to restart slideshows that are no longer being interacted with.
   */

  ThemeEditor.prototype._onSectionDeselect = function(event) {
    var ref, ref1;
    return (ref = this._findInstance(event)) != null ? (ref1 = ref.instanceHandler) != null ? typeof ref1.onSectionDeselect === "function" ? ref1.onSectionDeselect(event) : void 0 : void 0 : void 0;
  };


  /*
      Action: User has selected the block in the sidebar.
      Expected: Make sure the block is in view and stays
          in view while selected (scrolling happens automatically).
      Example: Can be used to to trigger a slideshow to bring a slide/block into view
   */

  ThemeEditor.prototype._onBlockSelect = function(event) {
    var ref, ref1;
    return (ref = this._findInstance(event)) != null ? (ref1 = ref.instanceHandler) != null ? typeof ref1.onBlockSelect === "function" ? ref1.onBlockSelect(event) : void 0 : void 0 : void 0;
  };


  /*
      Action: User has deselected the block in the sidebar.
      Expected: (None)
      Example: Resume a slideshow
   */

  ThemeEditor.prototype._onBlockDeselect = function(event) {
    var ref, ref1;
    return (ref = this._findInstance(event)) != null ? (ref1 = ref.instanceHandler) != null ? typeof ref1.onBlockDeselect === "function" ? ref1.onBlockDeselect(event) : void 0 : void 0 : void 0;
  };


  /*
      Auto initialisation of a section for the store front
   */

  ThemeEditor.prototype._sectionInit = function(instance) {
    var ref;
    return instance != null ? (ref = instance.instanceHandler) != null ? typeof ref.init === "function" ? ref.init(instance) : void 0 : void 0 : void 0;
  };


  /*
      Registration of a section
          - Takes a string parameter as the first argument which
            matches to `[data-section-type]`
  
       * Example
          @sections = new Sections()
          @sections.register('some-section-type', @someSectionClass)
   */

  ThemeEditor.prototype.register = function(type, instanceHandler) {

    /*
        Storage of a instanceHandler based on the sectionType allows _onSectionLoad
           to connect a new section to it's registered instanceHandler
     */
    this.instanceHandlers[type] = instanceHandler;
    return $("[data-section-type=" + type + "]").each((function(_this) {
      return function(index, container) {
        var $container;
        $container = $(container);
        return _this._sectionInit(_this._createInstance($container, instanceHandler));
      };
    })(this));
  };


  /*
      Public method to retrieve information on an instance based on the
      bubbled `event`
   */

  ThemeEditor.prototype.getInstance = function(event) {
    return this._findInstance(event);
  };

  return ThemeEditor;

})(Backbone.View);

window.SlideshowView = (function(superClass) {
  extend(SlideshowView, superClass);

  function SlideshowView() {
    return SlideshowView.__super__.constructor.apply(this, arguments);
  }

  SlideshowView.prototype.initialize = function() {
    this.$window = $(window);
    this.$document = $(document.body);
    this.mainHeader = $('[data-main-header]');
    this.headerLogo = $('[data-header-logo]', this.mainHeader);
    this.slideShow = null;
    this.$viewport = null;
    this.slideContainer = '[data-slideshow-container]';
    this.$slideContainer = $(this.slideContainer);
    this.slideSelector = '[data-slide]';
    this.enableNavigation = $(this.slideSelector).length > 1;
    this.$paginationContainer = $('[data-slideshow-pagination]');
    this.paginationItem = '[data-pagination-slide]';
    this.hasThumbnailPagination = this.$paginationContainer.length !== 0;
    this.slideShowDuration = parseInt(this.$el.attr('data-autoplay'), 10);
    this.sectionStyle = this.$el.attr('data-section-style') != null ? this.$el.attr('data-section-style') : false;
    this.setupHeader(this.$el);
    return this._init();
  };

  SlideshowView.prototype._init = function() {
    var flickityOptions;
    flickityOptions = {
      autoPlay: this.enableNavigation ? this.slideShowDuration : 0,
      cellSelector: this.slideSelector,
      cellAlign: 'center',
      draggable: this.enableNavigation,
      freeScroll: false,
      pageDots: !this.hasThumbnailPagination && this.enableNavigation,
      prevNextButtons: this.enableNavigation,
      setGallerySize: false,
      wrapAround: true
    };
    this.slideShow = new Flickity(this.slideContainer, flickityOptions);
    this.$slideShow = $(this.slideShow.element);
    this.$viewport = this.$slideShow.find('.flickity-viewport');
    this._bindSlideshow();
    if (this.sectionStyle) {
      this._sectionStyle(true);
    }
    if (this.hasThumbnailPagination) {
      this._bindPagination();
      return this._updatePagination(this.slideShow.selectedIndex);
    }
  };

  SlideshowView.prototype._bindSlideshow = function() {

    /*
        On slide change, find the new height of the slide and set it as the
        height of the slider
    
        TODO: On upgrade to Flickity 2, change this to `select`
     */
    this.slideShow.on('cellSelect', (function(_this) {
      return function() {
        _this.$slideShow.trigger('heightUpdate');
        return _this._updatePagination(_this.slideShow.selectedIndex);
      };
    })(this));
    this.$slideShow.on('heightUpdate', (function(_this) {
      return function() {
        return _this._setSlideHeight();
      };
    })(this));
    this.$slideShow.trigger('heightUpdate');
    return this.$window.on('resize.slideshow', window.ThemeUtils.debounce((function(_this) {
      return function() {
        return _this.$slideShow.trigger('heightUpdate');
      };
    })(this), 10));
  };

  SlideshowView.prototype._bindPagination = function() {
    return this.$paginationContainer.on('click', this.paginationItem, (function(_this) {
      return function(event) {
        var $target, slideTarget;
        event.preventDefault();
        $target = $(event.currentTarget);
        slideTarget = parseInt($target.attr('data-pagination-slide'), 10) - 1;
        _this.slideShow.select(slideTarget);
        return _this._updatePagination(slideTarget, $target);
      };
    })(this));
  };

  SlideshowView.prototype._updatePagination = function(slideTarget, $target) {
    if ($target == null) {
      $target = null;
    }
    if (typeof target === "undefined" || target === null) {
      $target = this.$paginationContainer.find(this.paginationItem).eq(slideTarget);
    }
    return $target.addClass('is-selected').siblings('.is-selected').removeClass('is-selected');
  };

  SlideshowView.prototype._setSlideHeight = function(minHeight) {
    var $element, $elementImage, $elementText, $pagination, $promotionBar, height, heights, imageHeight, isDesktop, isOpeningScreen, textHeight;
    if (minHeight == null) {
      minHeight = null;
    }
    isOpeningScreen = this.$el.hasClass('opening-screen');
    isDesktop = window.ThemeUtils.windowWidth() > 720;
    $element = $(this.slideShow.selectedElement);
    $elementImage = $element.find('.slide-image');
    $elementText = $element.find('.slide-text');
    $pagination = this.$el.find('.flickity-prev-next-button');
    if (isDesktop) {
      $pagination.height('');
    }
    if (isDesktop && isOpeningScreen) {
      $promotionBar = $('[data-promotion-bar]');
      if (!$promotionBar.length) {
        return;
      }
      height = window.innerHeight - $promotionBar.outerHeight();
      if (this.hasThumbnailPagination) {
        height = height - this.$paginationContainer.outerHeight(true);
      }
      $element.height(height);
      this.$viewport.height(height);
      this.$slideContainer.height(height);
      return this.$el.height(height);
    } else {
      heights = [];
      heights.push(minHeight);
      heights.push($element.height());
      imageHeight = $elementImage.outerHeight(true);
      textHeight = $elementText.length ? $elementText.outerHeight(true) : 0;
      if (isDesktop) {
        heights.push(imageHeight);
        heights.push(textHeight);
      }
      height = Math.max.apply(null, heights);
      if (imageHeight <= textHeight || $('.full-slideshow-wrapper').hasClass('content-width')) {
        height = imageHeight;
      }
      if (isOpeningScreen) {
        this.$slideContainer.height('');
        this.$el.height('');
      }
      if (isDesktop) {
        $element.height(height);
      } else {
        $element.height('');
        $pagination.height(textHeight ? imageHeight : height);
      }
      return this.$viewport.height(height);
    }
  };

  SlideshowView.prototype._sectionStyle = function(force) {
    var $section;
    $section = this.$el.parent('.shopify-section');
    return $section.toggleClass(this.sectionStyle, force);
  };


  /*
      Public method for SlideshowSection
          - Pauses the slideshow
          - Brings the current slide into view
   */

  SlideshowView.prototype.lockSlide = function(event) {
    var index;
    this.slideShow.pausePlayer();
    this.$el.toggleClass('slider-locked', true);
    index = parseInt($(event.target).attr('data-slide'), 10) - 1;
    return this.slideShow.select(index, false, true);
  };


  /*
      Public method for SlideshowSection
          - Unpause the slideshow
   */

  SlideshowView.prototype.unlockSlide = function() {
    this.slideShow.unpausePlayer();
    return this.$el.toggleClass('slider-locked', false);
  };


  /*
      Public method for SlideshowSection
          - Destroy the slideshow
          - Unbind events
   */

  SlideshowView.prototype.prepareRemove = function() {
    if (this.$paginationContainer.length) {
      this.$paginationContainer.off('click', this.paginationItem);
    }
    if (this.sectionStyle) {
      this._sectionStyle(false);
    }
    this.$window.off('resize.slideshow');
    this.$slideShow.off('heightUpdate');
    this.slideShow.off('cellSelect');
    return this.slideShow.destroy();
  };


  /*
      Triggers Logo swapping, or sticky header offsets
   */

  SlideshowView.prototype.setupHeader = function($el) {
    if (this.headerLogo.length) {
      $(document.body).trigger('swapLogo');
    }
    if ($el && ($el.attr('data-full-bleed-slideshow') != null)) {
      this.mainHeader.addClass('full-bleed-slideshow');
    } else {
      this.mainHeader.removeClass('full-bleed-slideshow');
    }
    return $(document.body).trigger('toggleStickyHeader', [$el]).trigger('toggleSlideShowHeader', [$el]);
  };

  SlideshowView.prototype.render = function() {};

  return SlideshowView;

})(Backbone.View);

window.SlideshowSection = (function(superClass) {
  extend(SlideshowSection, superClass);

  function SlideshowSection() {
    return SlideshowSection.__super__.constructor.apply(this, arguments);
  }

  SlideshowSection.prototype.initialize = function() {
    this.sections = new ThemeEditor();
    return this.sections.register('slideshow', this.slideShow(this.sections));
  };

  SlideshowSection.prototype.slideShow = function(sections) {
    return {
      instances: {},
      el: '[data-section-type="slideshow"]',
      init: function(instance) {
        return this.instances[instance.sectionId] = new SlideshowView({
          el: $(this.el)
        });
      },
      onSectionLoad: function(event) {
        var instance, ref;
        instance = sections.getInstance(event);
        if (!this.instances[instance.sectionId]) {
          this.init(instance);
          return (ref = this.instances[instance.sectionId]) != null ? typeof ref.setupHeader === "function" ? ref.setupHeader(null) : void 0 : void 0;
        }
      },
      onSectionUnload: function(event) {
        var instance, ref, ref1, ref2;
        instance = sections.getInstance(event);
        if ((ref = this.instances[instance.sectionId]) != null) {
          if (typeof ref.prepareRemove === "function") {
            ref.prepareRemove();
          }
        }
        if ((ref1 = this.instances[instance.sectionId]) != null) {
          if (typeof ref1.remove === "function") {
            ref1.remove();
          }
        }
        if ((ref2 = this.instances[instance.sectionId]) != null) {
          if (typeof ref2.setupHeader === "function") {
            ref2.setupHeader(null);
          }
        }
        return delete this.instances[instance.sectionId];
      },
      onSectionSelect: function(event) {
        var instance, ref;
        instance = sections.getInstance(event);
        return (ref = this.instances[instance.sectionId]) != null ? typeof ref.setupHeader === "function" ? ref.setupHeader(null) : void 0 : void 0;
      },
      onBlockSelect: function(event) {
        var instanceHandler;
        instanceHandler = this.instances[sections.getInstance(event).sectionId];
        return instanceHandler.lockSlide(event);
      },
      onBlockDeselect: function(event) {
        var instance, instanceHandler;
        instance = sections.getInstance(event);
        instanceHandler = this.instances[instance.sectionId];
        return instanceHandler.unlockSlide();
      }
    };
  };

  return SlideshowSection;

})(Backbone.View);



/*!
 * pxs-map v2.0.0
 * (c) 2018 undefined
 */

(function (global, factory) {
	typeof exports === 'object' && typeof module !== 'undefined' ? module.exports = factory(require('jquery')) :
	typeof define === 'function' && define.amd ? define(['jquery'], factory) :
	(global.PxsMap = factory(global.$));
}(this, (function ($) { 'use strict';

$ = $ && $.hasOwnProperty('default') ? $['default'] : $;

var justDebounce = debounce;

function debounce(fn, delay, at_start, guarantee) {
  var timeout;
  var args;
  var self;

  return function debounced() {
    self = this;
    args = Array.prototype.slice.call(arguments);

    if (timeout && (at_start || guarantee)) {
      return;
    } else if (!at_start) {
      clear();

      timeout = setTimeout(run, delay);
      return timeout;
    }

    timeout = setTimeout(clear, delay);
    fn.apply(self, args);

    function run() {
      clear();
      fn.apply(self, args);
    }

    function clear() {
      clearTimeout(timeout);
      timeout = null;
    }
  };
}

var classCallCheck = function (instance, Constructor) {
  if (!(instance instanceof Constructor)) {
    throw new TypeError("Cannot call a class as a function");
  }
};

var createClass = function () {
  function defineProperties(target, props) {
    for (var i = 0; i < props.length; i++) {
      var descriptor = props[i];
      descriptor.enumerable = descriptor.enumerable || false;
      descriptor.configurable = true;
      if ("value" in descriptor) descriptor.writable = true;
      Object.defineProperty(target, descriptor.key, descriptor);
    }
  }

  return function (Constructor, protoProps, staticProps) {
    if (protoProps) defineProperties(Constructor.prototype, protoProps);
    if (staticProps) defineProperties(Constructor, staticProps);
    return Constructor;
  };
}();

var PxsMap = function () {
  function PxsMap(section) {
    var _this = this;

    classCallCheck(this, PxsMap);

    this.$el = $('[data-map]', section.el);
    this.settings = section.data;
    this.map = null;
    this.center = null;

    this.$container = $('[data-map-container]', this.$el);

    // Scale so range is 12 ~ 17, rather than 1 to 6
    this.zoom = 11 + parseInt(this.settings.zoom, 10);
    if (isNaN(this.zoom)) this.zoom = 13;

    this.colors = null;

    if (this.settings.colors) {
      this.colors = this.settings.colors;
    }

    this.resize = this.resize.bind(this);

    this.address = this.settings.address;
    this.apiKey = this.settings.api_key;

    if (this.apiKey) {
      if (window.googleMaps === undefined) {
        window.googleMaps = true;

        $.getScript('https://maps.googleapis.com/maps/api/js?key=' + this.apiKey).done(function () {
          _this._createMap();
        }).fail(function (status) {
          console.error(status);
        });
      } else {
        this._createMap();
      }
    }
  }

  createClass(PxsMap, [{
    key: '_createMap',
    value: function _createMap() {
      var _this2 = this;

      return this.geolocate().done(function (results) {
        _this2.map = new google.maps.Map(_this2.$container.get(0), {
          center: results[0].geometry.location,
          clickableIcons: false,
          disableDefaultUI: true,
          disableDoubleClickZoom: true,
          gestureHandling: 'none',
          keyboardShortcuts: false,
          maxZoom: _this2.zoom,
          minZoom: _this2.zoom,
          scrollWheel: false,
          styles: _this2._getMapStyles(),
          zoom: _this2.zoom,
          zoomControl: false
        });
        _this2.center = _this2.map.getCenter();
        _this2.map.panBy(0, 0);

        new google.maps.Marker({
          clickable: false,
          map: _this2.map,
          position: _this2.center
        });

        google.maps.event.addDomListener(window, 'resize', justDebounce(_this2.resize, 250, true, true));
      }).fail(function (status) {
        var usageLimits = 'https://developers.google.com/maps/faq#usagelimits';
        var errorMessage = void 0;

        switch (status) {
          case 'ZERO_RESULTS':
            errorMessage = '<p>Unable to find the address:</p> ' + _this2.address;
            break;
          case 'OVER_QUERY_LIMIT':
            errorMessage = '\n              <p>Unable to load Google Maps, you have reached your usage limit.</p>\n              <p>\n                Please visit\n                <a href="' + usageLimits + '" target="_blank">' + usageLimits + '</a>\n                for more details.\n              </p>\n            ';
            break;
          default:
            errorMessage = 'Unable to load Google Maps.';
            break;
        }

        _this2.displayErrorInThemeEditor(errorMessage, status);
      });
    }
  }, {
    key: 'geolocate',
    value: function geolocate() {
      var deferred = $.Deferred();
      var geocoder = new google.maps.Geocoder();

      geocoder.geocode({ address: this.address }, function (results, status) {
        if (status !== google.maps.GeocoderStatus.OK) {
          deferred.reject(status);
        }

        deferred.resolve(results);
      });

      return deferred;
    }
  }, {
    key: 'resize',
    value: function resize() {
      if (this.map) {
        google.maps.event.trigger(this.map, 'resize');
        this.map.setCenter(this.center);
        this.map.panBy(0, 100);
      }
    }
  }, {
    key: 'onSectionUnload',
    value: function onSectionUnload() {
      if (this.map) {
        google.maps.event.clearListeners(this.map, 'resize');
      }
    }
  }, {
    key: '_getMapStyles',
    value: function _getMapStyles() {
      if (!this.colors) {
        return;
      }

      return [{ elementType: 'geometry', stylers: [{ color: this.colors.e }] }, { elementType: 'labels.icon', stylers: [{ visibility: 'off' }] }, { elementType: 'labels.text.fill', stylers: [{ color: this.colors.a }] }, { elementType: 'labels.text.stroke', stylers: [{ color: this.colors.e }] }, { featureType: 'administrative', elementType: 'geometry', stylers: [{ visibility: 'off' }] }, { featureType: 'administrative.country', stylers: [{ visibility: 'off' }] }, { featureType: 'administrative.land_parcel', stylers: [{ visibility: 'off' }] }, { featureType: 'administrative.neighborhood', stylers: [{ visibility: 'off' }] }, { featureType: 'administrative.locality', stylers: [{ visibility: 'off' }] }, { featureType: 'poi', stylers: [{ visibility: 'off' }] }, { featureType: 'road', elementType: 'geometry.fill', stylers: [{ color: this.colors.d }] }, { featureType: 'road', elementType: 'labels.icon', stylers: [{ visibility: 'off' }] }, { featureType: 'road.arterial', elementType: 'geometry', stylers: [{ color: this.colors.c }] }, { featureType: 'road.highway', elementType: 'geometry', stylers: [{ color: this.colors.b }] }, { featureType: 'road.highway.controlled_access', stylers: [{ visibility: 'off' }] }, { featureType: 'road.local', elementType: 'labels.text.fill', stylers: [{ color: this.colors.b }] }, { featureType: 'road.local', elementType: 'labels.text.stroke', stylers: [{ color: this.colors.e }] }, { featureType: 'transit', stylers: [{ visibility: 'off' }] }, { featureType: 'water', elementType: 'geometry', stylers: [{ color: this.colors.f }] }];
    }
  }, {
    key: 'displayErrorInThemeEditor',
    value: function displayErrorInThemeEditor(errorMessage) {
      var isThemeEditor = window.Shopify && window.Shopify.designMode;

      if (!isThemeEditor) {
        return;
      }

      this.$container.html('<div class="map-error-message">' + errorMessage + '</div>');
    }
  }]);
  return PxsMap;
}();

return PxsMap;

})));

;


    /**
     * Copyright 2016 Google Inc. All Rights Reserved.
     *
     * Licensed under the W3C SOFTWARE AND DOCUMENT NOTICE AND LICENSE.
     *
     *  https://www.w3.org/Consortium/Legal/2015/copyright-software-and-document
     *
     */
    
    (function(window, document) {
    'use strict';
    
    
    // Exits early if all IntersectionObserver and IntersectionObserverEntry
    // features are natively supported.
    if ('IntersectionObserver' in window &&
        'IntersectionObserverEntry' in window &&
        'intersectionRatio' in window.IntersectionObserverEntry.prototype) {
    
      // Minimal polyfill for Edge 15's lack of `isIntersecting`
      // See: https://github.com/w3c/IntersectionObserver/issues/211
      if (!('isIntersecting' in window.IntersectionObserverEntry.prototype)) {
        Object.defineProperty(window.IntersectionObserverEntry.prototype,
          'isIntersecting', {
          get: function () {
            return this.intersectionRatio > 0;
          }
        });
      }
      return;
    }
    
    
    /**
     * An IntersectionObserver registry. This registry exists to hold a strong
     * reference to IntersectionObserver instances currently observering a target
     * element. Without this registry, instances without another reference may be
     * garbage collected.
     */
    var registry = [];
    
    
    /**
     * Creates the global IntersectionObserverEntry constructor.
     * https://w3c.github.io/IntersectionObserver/#intersection-observer-entry
     * @param {Object} entry A dictionary of instance properties.
     * @constructor
     */
    function IntersectionObserverEntry(entry) {
      this.time = entry.time;
      this.target = entry.target;
      this.rootBounds = entry.rootBounds;
      this.boundingClientRect = entry.boundingClientRect;
      this.intersectionRect = entry.intersectionRect || getEmptyRect();
      this.isIntersecting = !!entry.intersectionRect;
    
      // Calculates the intersection ratio.
      var targetRect = this.boundingClientRect;
      var targetArea = targetRect.width * targetRect.height;
      var intersectionRect = this.intersectionRect;
      var intersectionArea = intersectionRect.width * intersectionRect.height;
    
      // Sets intersection ratio.
      if (targetArea) {
        this.intersectionRatio = intersectionArea / targetArea;
      } else {
        // If area is zero and is intersecting, sets to 1, otherwise to 0
        this.intersectionRatio = this.isIntersecting ? 1 : 0;
      }
    }
    
    
    /**
     * Creates the global IntersectionObserver constructor.
     * https://w3c.github.io/IntersectionObserver/#intersection-observer-interface
     * @param {Function} callback The function to be invoked after intersection
     *     changes have queued. The function is not invoked if the queue has
     *     been emptied by calling the `takeRecords` method.
     * @param {Object=} opt_options Optional configuration options.
     * @constructor
     */
    function IntersectionObserver(callback, opt_options) {
    
      var options = opt_options || {};
    
      if (typeof callback != 'function') {
        throw new Error('callback must be a function');
      }
    
      if (options.root && options.root.nodeType != 1) {
        throw new Error('root must be an Element');
      }
    
      // Binds and throttles `this._checkForIntersections`.
      this._checkForIntersections = throttle(
          this._checkForIntersections.bind(this), this.THROTTLE_TIMEOUT);
    
      // Private properties.
      this._callback = callback;
      this._observationTargets = [];
      this._queuedEntries = [];
      this._rootMarginValues = this._parseRootMargin(options.rootMargin);
    
      // Public properties.
      this.thresholds = this._initThresholds(options.threshold);
      this.root = options.root || null;
      this.rootMargin = this._rootMarginValues.map(function(margin) {
        return margin.value + margin.unit;
      }).join(' ');
    }
    
    
    /**
     * The minimum interval within which the document will be checked for
     * intersection changes.
     */
    IntersectionObserver.prototype.THROTTLE_TIMEOUT = 100;
    
    
    /**
     * The frequency in which the polyfill polls for intersection changes.
     * this can be updated on a per instance basis and must be set prior to
     * calling `observe` on the first target.
     */
    IntersectionObserver.prototype.POLL_INTERVAL = null;
    
    /**
     * Use a mutation observer on the root element
     * to detect intersection changes.
     */
    IntersectionObserver.prototype.USE_MUTATION_OBSERVER = true;
    
    
    /**
     * Starts observing a target element for intersection changes based on
     * the thresholds values.
     * @param {Element} target The DOM element to observe.
     */
    IntersectionObserver.prototype.observe = function(target) {
      var isTargetAlreadyObserved = this._observationTargets.some(function(item) {
        return item.element == target;
      });
    
      if (isTargetAlreadyObserved) {
        return;
      }
    
      if (!(target && target.nodeType == 1)) {
        throw new Error('target must be an Element');
      }
    
      this._registerInstance();
      this._observationTargets.push({element: target, entry: null});
      this._monitorIntersections();
      this._checkForIntersections();
    };
    
    
    /**
     * Stops observing a target element for intersection changes.
     * @param {Element} target The DOM element to observe.
     */
    IntersectionObserver.prototype.unobserve = function(target) {
      this._observationTargets =
          this._observationTargets.filter(function(item) {
    
        return item.element != target;
      });
      if (!this._observationTargets.length) {
        this._unmonitorIntersections();
        this._unregisterInstance();
      }
    };
    
    
    /**
     * Stops observing all target elements for intersection changes.
     */
    IntersectionObserver.prototype.disconnect = function() {
      this._observationTargets = [];
      this._unmonitorIntersections();
      this._unregisterInstance();
    };
    
    
    /**
     * Returns any queue entries that have not yet been reported to the
     * callback and clears the queue. This can be used in conjunction with the
     * callback to obtain the absolute most up-to-date intersection information.
     * @return {Array} The currently queued entries.
     */
    IntersectionObserver.prototype.takeRecords = function() {
      var records = this._queuedEntries.slice();
      this._queuedEntries = [];
      return records;
    };
    
    
    /**
     * Accepts the threshold value from the user configuration object and
     * returns a sorted array of unique threshold values. If a value is not
     * between 0 and 1 and error is thrown.
     * @private
     * @param {Array|number=} opt_threshold An optional threshold value or
     *     a list of threshold values, defaulting to [0].
     * @return {Array} A sorted list of unique and valid threshold values.
     */
    IntersectionObserver.prototype._initThresholds = function(opt_threshold) {
      var threshold = opt_threshold || [0];
      if (!Array.isArray(threshold)) threshold = [threshold];
    
      return threshold.sort().filter(function(t, i, a) {
        if (typeof t != 'number' || isNaN(t) || t < 0 || t > 1) {
          throw new Error('threshold must be a number between 0 and 1 inclusively');
        }
        return t !== a[i - 1];
      });
    };
    
    
    /**
     * Accepts the rootMargin value from the user configuration object
     * and returns an array of the four margin values as an object containing
     * the value and unit properties. If any of the values are not properly
     * formatted or use a unit other than px or %, and error is thrown.
     * @private
     * @param {string=} opt_rootMargin An optional rootMargin value,
     *     defaulting to '0px'.
     * @return {Array<Object>} An array of margin objects with the keys
     *     value and unit.
     */
    IntersectionObserver.prototype._parseRootMargin = function(opt_rootMargin) {
      var marginString = opt_rootMargin || '0px';
      var margins = marginString.split(/\s+/).map(function(margin) {
        var parts = /^(-?\d*\.?\d+)(px|%)$/.exec(margin);
        if (!parts) {
          throw new Error('rootMargin must be specified in pixels or percent');
        }
        return {value: parseFloat(parts[1]), unit: parts[2]};
      });
    
      // Handles shorthand.
      margins[1] = margins[1] || margins[0];
      margins[2] = margins[2] || margins[0];
      margins[3] = margins[3] || margins[1];
    
      return margins;
    };
    
    
    /**
     * Starts polling for intersection changes if the polling is not already
     * happening, and if the page's visibilty state is visible.
     * @private
     */
    IntersectionObserver.prototype._monitorIntersections = function() {
      if (!this._monitoringIntersections) {
        this._monitoringIntersections = true;
    
        // If a poll interval is set, use polling instead of listening to
        // resize and scroll events or DOM mutations.
        if (this.POLL_INTERVAL) {
          this._monitoringInterval = setInterval(
              this._checkForIntersections, this.POLL_INTERVAL);
        }
        else {
          addEvent(window, 'resize', this._checkForIntersections, true);
          addEvent(document, 'scroll', this._checkForIntersections, true);
    
          if (this.USE_MUTATION_OBSERVER && 'MutationObserver' in window) {
            this._domObserver = new MutationObserver(this._checkForIntersections);
            this._domObserver.observe(document, {
              attributes: true,
              childList: true,
              characterData: true,
              subtree: true
            });
          }
        }
      }
    };
    
    
    /**
     * Stops polling for intersection changes.
     * @private
     */
    IntersectionObserver.prototype._unmonitorIntersections = function() {
      if (this._monitoringIntersections) {
        this._monitoringIntersections = false;
    
        clearInterval(this._monitoringInterval);
        this._monitoringInterval = null;
    
        removeEvent(window, 'resize', this._checkForIntersections, true);
        removeEvent(document, 'scroll', this._checkForIntersections, true);
    
        if (this._domObserver) {
          this._domObserver.disconnect();
          this._domObserver = null;
        }
      }
    };
    
    
    /**
     * Scans each observation target for intersection changes and adds them
     * to the internal entries queue. If new entries are found, it
     * schedules the callback to be invoked.
     * @private
     */
    IntersectionObserver.prototype._checkForIntersections = function() {
      var rootIsInDom = this._rootIsInDom();
      var rootRect = rootIsInDom ? this._getRootRect() : getEmptyRect();
    
      this._observationTargets.forEach(function(item) {
        var target = item.element;
        var targetRect = getBoundingClientRect(target);
        var rootContainsTarget = this._rootContainsTarget(target);
        var oldEntry = item.entry;
        var intersectionRect = rootIsInDom && rootContainsTarget &&
            this._computeTargetAndRootIntersection(target, rootRect);
    
        var newEntry = item.entry = new IntersectionObserverEntry({
          time: now(),
          target: target,
          boundingClientRect: targetRect,
          rootBounds: rootRect,
          intersectionRect: intersectionRect
        });
    
        if (!oldEntry) {
          this._queuedEntries.push(newEntry);
        } else if (rootIsInDom && rootContainsTarget) {
          // If the new entry intersection ratio has crossed any of the
          // thresholds, add a new entry.
          if (this._hasCrossedThreshold(oldEntry, newEntry)) {
            this._queuedEntries.push(newEntry);
          }
        } else {
          // If the root is not in the DOM or target is not contained within
          // root but the previous entry for this target had an intersection,
          // add a new record indicating removal.
          if (oldEntry && oldEntry.isIntersecting) {
            this._queuedEntries.push(newEntry);
          }
        }
      }, this);
    
      if (this._queuedEntries.length) {
        this._callback(this.takeRecords(), this);
      }
    };
    
    
    /**
     * Accepts a target and root rect computes the intersection between then
     * following the algorithm in the spec.
     * TODO(philipwalton): at this time clip-path is not considered.
     * https://w3c.github.io/IntersectionObserver/#calculate-intersection-rect-algo
     * @param {Element} target The target DOM element
     * @param {Object} rootRect The bounding rect of the root after being
     *     expanded by the rootMargin value.
     * @return {?Object} The final intersection rect object or undefined if no
     *     intersection is found.
     * @private
     */
    IntersectionObserver.prototype._computeTargetAndRootIntersection =
        function(target, rootRect) {
    
      // If the element isn't displayed, an intersection can't happen.
      if (window.getComputedStyle(target).display == 'none') return;
    
      var targetRect = getBoundingClientRect(target);
      var intersectionRect = targetRect;
      var parent = getParentNode(target);
      var atRoot = false;
    
      while (!atRoot) {
        var parentRect = null;
        var parentComputedStyle = parent.nodeType == 1 ?
            window.getComputedStyle(parent) : {};
    
        // If the parent isn't displayed, an intersection can't happen.
        if (parentComputedStyle.display == 'none') return;
    
        if (parent == this.root || parent == document) {
          atRoot = true;
          parentRect = rootRect;
        } else {
          // If the element has a non-visible overflow, and it's not the <body>
          // or <html> element, update the intersection rect.
          // Note: <body> and <html> cannot be clipped to a rect that's not also
          // the document rect, so no need to compute a new intersection.
          if (parent != document.body &&
              parent != document.documentElement &&
              parentComputedStyle.overflow != 'visible') {
            parentRect = getBoundingClientRect(parent);
          }
        }
    
        // If either of the above conditionals set a new parentRect,
        // calculate new intersection data.
        if (parentRect) {
          intersectionRect = computeRectIntersection(parentRect, intersectionRect);
    
          if (!intersectionRect) break;
        }
        parent = getParentNode(parent);
      }
      return intersectionRect;
    };
    
    
    /**
     * Returns the root rect after being expanded by the rootMargin value.
     * @return {Object} The expanded root rect.
     * @private
     */
    IntersectionObserver.prototype._getRootRect = function() {
      var rootRect;
      if (this.root) {
        rootRect = getBoundingClientRect(this.root);
      } else {
        // Use <html>/<body> instead of window since scroll bars affect size.
        var html = document.documentElement;
        var body = document.body;
        rootRect = {
          top: 0,
          left: 0,
          right: html.clientWidth || body.clientWidth,
          width: html.clientWidth || body.clientWidth,
          bottom: html.clientHeight || body.clientHeight,
          height: html.clientHeight || body.clientHeight
        };
      }
      return this._expandRectByRootMargin(rootRect);
    };
    
    
    /**
     * Accepts a rect and expands it by the rootMargin value.
     * @param {Object} rect The rect object to expand.
     * @return {Object} The expanded rect.
     * @private
     */
    IntersectionObserver.prototype._expandRectByRootMargin = function(rect) {
      var margins = this._rootMarginValues.map(function(margin, i) {
        return margin.unit == 'px' ? margin.value :
            margin.value * (i % 2 ? rect.width : rect.height) / 100;
      });
      var newRect = {
        top: rect.top - margins[0],
        right: rect.right + margins[1],
        bottom: rect.bottom + margins[2],
        left: rect.left - margins[3]
      };
      newRect.width = newRect.right - newRect.left;
      newRect.height = newRect.bottom - newRect.top;
    
      return newRect;
    };
    
    
    /**
     * Accepts an old and new entry and returns true if at least one of the
     * threshold values has been crossed.
     * @param {?IntersectionObserverEntry} oldEntry The previous entry for a
     *    particular target element or null if no previous entry exists.
     * @param {IntersectionObserverEntry} newEntry The current entry for a
     *    particular target element.
     * @return {boolean} Returns true if a any threshold has been crossed.
     * @private
     */
    IntersectionObserver.prototype._hasCrossedThreshold =
        function(oldEntry, newEntry) {
    
      // To make comparing easier, an entry that has a ratio of 0
      // but does not actually intersect is given a value of -1
      var oldRatio = oldEntry && oldEntry.isIntersecting ?
          oldEntry.intersectionRatio || 0 : -1;
      var newRatio = newEntry.isIntersecting ?
          newEntry.intersectionRatio || 0 : -1;
    
      // Ignore unchanged ratios
      if (oldRatio === newRatio) return;
    
      for (var i = 0; i < this.thresholds.length; i++) {
        var threshold = this.thresholds[i];
    
        // Return true if an entry matches a threshold or if the new ratio
        // and the old ratio are on the opposite sides of a threshold.
        if (threshold == oldRatio || threshold == newRatio ||
            threshold < oldRatio !== threshold < newRatio) {
          return true;
        }
      }
    };
    
    
    /**
     * Returns whether or not the root element is an element and is in the DOM.
     * @return {boolean} True if the root element is an element and is in the DOM.
     * @private
     */
    IntersectionObserver.prototype._rootIsInDom = function() {
      return !this.root || containsDeep(document, this.root);
    };
    
    
    /**
     * Returns whether or not the target element is a child of root.
     * @param {Element} target The target element to check.
     * @return {boolean} True if the target element is a child of root.
     * @private
     */
    IntersectionObserver.prototype._rootContainsTarget = function(target) {
      return containsDeep(this.root || document, target);
    };
    
    
    /**
     * Adds the instance to the global IntersectionObserver registry if it isn't
     * already present.
     * @private
     */
    IntersectionObserver.prototype._registerInstance = function() {
      if (registry.indexOf(this) < 0) {
        registry.push(this);
      }
    };
    
    
    /**
     * Removes the instance from the global IntersectionObserver registry.
     * @private
     */
    IntersectionObserver.prototype._unregisterInstance = function() {
      var index = registry.indexOf(this);
      if (index != -1) registry.splice(index, 1);
    };
    
    
    /**
     * Returns the result of the performance.now() method or null in browsers
     * that don't support the API.
     * @return {number} The elapsed time since the page was requested.
     */
    function now() {
      return window.performance && performance.now && performance.now();
    }
    
    
    /**
     * Throttles a function and delays its executiong, so it's only called at most
     * once within a given time period.
     * @param {Function} fn The function to throttle.
     * @param {number} timeout The amount of time that must pass before the
     *     function can be called again.
     * @return {Function} The throttled function.
     */
    function throttle(fn, timeout) {
      var timer = null;
      return function () {
        if (!timer) {
          timer = setTimeout(function() {
            fn();
            timer = null;
          }, timeout);
        }
      };
    }
    
    
    /**
     * Adds an event handler to a DOM node ensuring cross-browser compatibility.
     * @param {Node} node The DOM node to add the event handler to.
     * @param {string} event The event name.
     * @param {Function} fn The event handler to add.
     * @param {boolean} opt_useCapture Optionally adds the even to the capture
     *     phase. Note: this only works in modern browsers.
     */
    function addEvent(node, event, fn, opt_useCapture) {
      if (typeof node.addEventListener == 'function') {
        node.addEventListener(event, fn, opt_useCapture || false);
      }
      else if (typeof node.attachEvent == 'function') {
        node.attachEvent('on' + event, fn);
      }
    }
    
    
    /**
     * Removes a previously added event handler from a DOM node.
     * @param {Node} node The DOM node to remove the event handler from.
     * @param {string} event The event name.
     * @param {Function} fn The event handler to remove.
     * @param {boolean} opt_useCapture If the event handler was added with this
     *     flag set to true, it should be set to true here in order to remove it.
     */
    function removeEvent(node, event, fn, opt_useCapture) {
      if (typeof node.removeEventListener == 'function') {
        node.removeEventListener(event, fn, opt_useCapture || false);
      }
      else if (typeof node.detatchEvent == 'function') {
        node.detatchEvent('on' + event, fn);
      }
    }
    
    
    /**
     * Returns the intersection between two rect objects.
     * @param {Object} rect1 The first rect.
     * @param {Object} rect2 The second rect.
     * @return {?Object} The intersection rect or undefined if no intersection
     *     is found.
     */
    function computeRectIntersection(rect1, rect2) {
      var top = Math.max(rect1.top, rect2.top);
      var bottom = Math.min(rect1.bottom, rect2.bottom);
      var left = Math.max(rect1.left, rect2.left);
      var right = Math.min(rect1.right, rect2.right);
      var width = right - left;
      var height = bottom - top;
    
      return (width >= 0 && height >= 0) && {
        top: top,
        bottom: bottom,
        left: left,
        right: right,
        width: width,
        height: height
      };
    }
    
    
    /**
     * Shims the native getBoundingClientRect for compatibility with older IE.
     * @param {Element} el The element whose bounding rect to get.
     * @return {Object} The (possibly shimmed) rect of the element.
     */
    function getBoundingClientRect(el) {
      var rect;
    
      try {
        rect = el.getBoundingClientRect();
      } catch (err) {
        // Ignore Windows 7 IE11 "Unspecified error"
        // https://github.com/w3c/IntersectionObserver/pull/205
      }
    
      if (!rect) return getEmptyRect();
    
      // Older IE
      if (!(rect.width && rect.height)) {
        rect = {
          top: rect.top,
          right: rect.right,
          bottom: rect.bottom,
          left: rect.left,
          width: rect.right - rect.left,
          height: rect.bottom - rect.top
        };
      }
      return rect;
    }
    
    
    /**
     * Returns an empty rect object. An empty rect is returned when an element
     * is not in the DOM.
     * @return {Object} The empty rect.
     */
    function getEmptyRect() {
      return {
        top: 0,
        bottom: 0,
        left: 0,
        right: 0,
        width: 0,
        height: 0
      };
    }
    
    /**
     * Checks to see if a parent element contains a child elemnt (including inside
     * shadow DOM).
     * @param {Node} parent The parent element.
     * @param {Node} child The child element.
     * @return {boolean} True if the parent node contains the child node.
     */
    function containsDeep(parent, child) {
      var node = child;
      while (node) {
        if (node == parent) return true;
    
        node = getParentNode(node);
      }
      return false;
    }
    
    
    /**
     * Gets the parent node of an element or its host element if the parent node
     * is a shadow root.
     * @param {Node} node The node whose parent to get.
     * @return {Node|null} The parent node or null if no parent exists.
     */
    function getParentNode(node) {
      var parent = node.parentNode;
    
      if (parent && parent.nodeType == 11 && parent.host) {
        // If the parent is a shadow root, return the host element.
        return parent.host;
      }
      return parent;
    }
    
    
    // Exposes the constructors globally.
    window.IntersectionObserver = IntersectionObserver;
    window.IntersectionObserverEntry = IntersectionObserverEntry;
    
    }(window, document));
    
    /*!
     * rimg v2.1.0
     * (c) 2018 Pixel Union
     */
    (function (global, factory) {
    	typeof exports === 'object' && typeof module !== 'undefined' ? module.exports = factory() :
    	typeof define === 'function' && define.amd ? define(factory) :
    	(global.rimg = factory());
    }(this, (function () { 'use strict';
    
    /**
     * The default template render function. Turns a template string into an image
     * URL.
     *
     * @param {String} template
     * @param {Size} size
     * @returns {String}
     */
    function defaultTemplateRender(template, size) {
      return template.replace('{size}', size.width + 'x' + size.height);
    }
    
    /**
     * @type Settings
     */
    var defaults = {
      scale: 1,
      template: false,
      templateRender: defaultTemplateRender,
      max: { width: Infinity, height: Infinity },
      round: 32,
      placeholder: false
    };
    
    /**
     * Get a data attribute value from an element, with a default fallback and
     * sanitization step.
     *
     * @param {Element} el
     *
     * @param {String} name
     *        The data attribute name.
     *
     * @param {Object} options
     *        An object holding fallback values if the data attribute does not
     *        exist. If this object doesn't have the property, we further fallback
     *        to our defaults.
     *
     * @param {Function} [sanitize]
     *        A function to sanitize the data attribute value with.
     *
     * @returns {String|*}
     */
    function getData(el, name, options, sanitize) {
      var attr = 'data-rimg-' + name;
      if (!el.hasAttribute(attr)) return options[name] || defaults[name];
    
      var value = el.getAttribute(attr);
    
      return sanitize ? sanitize(value) : value;
    }
    
    /**
     * Sanitize data attributes that represent a size (in the form of `10x10`).
     *
     * @param {String} value
     * @returns {Object} An object with `width` and `height` properties.
     */
    function parseSize(value) {
      value = value.split('x');
      return { width: parseInt(value[0], 10), height: parseInt(value[1], 10) };
    }
    
    /**
     * Loads information about an element.
     *
     * Options can be set on the element itself using data attributes, or through
     * the `options` parameter. Data attributes take priority.
     *
     * @param {HTMLElement} el
     * @param {Settings} options
     * @returns {Item}
     */
    function parseItem(el) {
      var options = arguments.length > 1 && arguments[1] !== undefined ? arguments[1] : {};
    
      var isImage = el.hasAttribute('data-rimg-template');
    
      /**
       * @typedef {Settings} Item
       */
      return {
        el: el,
    
        // Type of element
        isImage: isImage,
        isBackgroundImage: isImage && el.tagName !== 'IMG',
    
        // Image scale
        scale: getData(el, 'scale', options),
    
        // Device density
        density: window.devicePixelRatio || 1,
    
        // Image template URL
        template: getData(el, 'template', options),
        templateRender: options.templateRender || defaults.templateRender,
    
        // Maximum image dimensions
        max: getData(el, 'max', options, parseSize),
    
        // Round image dimensions to the nearest multiple
        round: getData(el, 'round', options),
    
        // Placeholder image dimensions
        placeholder: getData(el, 'placeholder', options, parseSize)
      };
    }
    
    /**
     * Round to the nearest multiple.
     *
     * This is so we don't tax the image server too much.
     *
     * @param {Number} size The size, in pixels.
     * @param {Number} multiple The multiple to round to the nearest.
     * @returns {Number}
     */
    function roundSize(size, multiple) {
      return Math.ceil(size / multiple) * multiple;
    }
    
    /**
     * Get the size of an element.
     *
     * If it is too small, it's parent element is checked, and so on. This helps
     * avoid the situation where an element doesn't have a size yet or is positioned
     * out of the layout.
     *
     * @param {HTMLElement} el
     * @return {Object} size
     * @return {Number} size.width The width, in pixels.
     * @return {Number} size.height The height, in pixels.
     */
    function getElementSize(el) {
      var size = { width: 0, height: 0 };
    
      while (el) {
        size.width = el.offsetWidth;
        size.height = el.offsetHeight;
        if (size.width > 20 && size.height > 20) break;
        el = el.parentNode;
      }
    
      return size;
    }
    
    /**
     * Trigger a custom event.
     *
     * Note: this approach is deprecated, but still required to support older
     * browsers such as IE 10.
     *
     * @see https://developer.mozilla.org/en-US/docs/Web/Guide/Events/Creating_and_triggering_events
     *
     * @param {HTMLElement} el
     *        The element to trigger the event on.
     *
     * @param {String} name
     *        The event name.
     *
     * @returns {Boolean}
     *          True if the event was canceled.
     */
    function trigger(el, name) {
      var event = document.createEvent('Event');
      event.initEvent(name, true, true);
      return !el.dispatchEvent(event);
    }
    
    /**
     * Return the maximum supported density of the image, given the container.
     *
     * @param {Item} item
     * @param {Size} size
     */
    function supportedDensity(item, size) {
      return Math.min(Math.min(Math.max(item.max.width / size.width, 1), item.density), Math.min(Math.max(item.max.height / size.height, 1), item.density)).toFixed(2);
    }
    
    /**
     * Set the image URL on the element. Supports background images and `srcset`.
     *
     * @param {Item} item
     * @param {Size} size
     * @param {Boolean} isPlaceholder
     */
    function setImage(item, size, isPlaceholder, onLoad) {
      var render = item.templateRender;
      var density = isPlaceholder ? 1 : supportedDensity(item, size);
      var round = isPlaceholder ? 1 : item.round;
    
      var width = roundSize(size.width * density, round);
      var height = roundSize(size.height * density, round);
      var displaySize = width > item.max.width || height > item.max.height ? { width: item.max.width, height: item.max.height } : { width: width, height: height };
    
      var url = render(item.template, displaySize);
    
      // On load callback
      var image = new Image();
      image.onload = onLoad;
      image.src = url;
    
      // Set image
      if (item.isBackgroundImage) {
        item.el.style.backgroundImage = 'url(\'' + url + '\')';
      } else {
        item.el.setAttribute('srcset', url + ' ' + density + 'x');
      }
    }
    
    /**
     * Load the image, set loaded status, and trigger the load event.
     *
     * @fires rimg:load
     * @fires rimg:error
     * @param {Item} item
     * @param {Size} size
     */
    function loadFullImage(item, size) {
      var el = item.el;
    
      setImage(item, size, false, function (event) {
        if (event.type === 'load') {
          el.setAttribute('data-rimg', 'loaded');
        } else {
          el.setAttribute('data-rimg', 'error');
          trigger(el, 'rimg:error');
        }
    
        trigger(el, 'rimg:load');
      });
    }
    
    /**
     * Load in a responsive image.
     *
     * Sets the image's `srcset` attribute to the final image URLs, calculated based
     * on the actual size the image is being shown at.
     *
     * @fires rimg:loading
     *        The image URLs have been set and we are waiting for them to load.
     *
     * @fires rimg:loaded
     *        The final image has loaded.
     *
     * @fires rimg:error
     *        The final image failed loading.
     *
     * @param {Item} item
     */
    function loadImage(item) {
      var el = item.el;
    
      // Already loaded?
      var status = el.getAttribute('data-rimg');
      if (status === 'loading' || status === 'loaded') return;
    
      // Is the SVG loaded?
      if (!el.complete && !item.isBackgroundImage) {
        // Wait for the load event, then call load image
        el.addEventListener('load', function cb() {
          el.removeEventListener('load', cb);
          loadImage(item);
        });
    
        return;
      }
    
      // Trigger loading event, and stop if cancelled
      if (trigger(el, 'rimg:loading')) return;
    
      // Mark as loading
      el.setAttribute('data-rimg', 'loading');
    
      // Get element size. This is used as the ideal display size.
      var size = getElementSize(item.el);
    
      size.width *= item.scale;
      size.height *= item.scale;
    
      if (item.placeholder) {
        // Load a placeholder image first, followed by the full image. Force the
        // element to keep its dimensions while it loads. If the image is smaller
        // than the element size, use the image's size. Density is taken into account
        // for HiDPI devices to avoid blurry images.
        if (!item.isBackgroundImage) {
          el.setAttribute('width', Math.min(Math.floor(item.max.width / item.density), size.width));
          el.setAttribute('height', Math.min(Math.floor(item.max.height / item.density), size.height));
        }
    
        setImage(item, item.placeholder, true, function () {
          return loadFullImage(item, size);
        });
      } else {
        loadFullImage(item, size);
      }
    }
    
    /**
     * Prepare an element to be displayed on the screen.
     *
     * Images have special logic applied to them to swap out the different sources.
     *
     * @fires rimg:enter
     *        The element is entering the viewport.
     *
     * @param {HTMLElement} el
     * @param {Settings} options
     */
    function load(el, options) {
      if (!el) return;
      trigger(el, 'rimg:enter');
    
      var item = parseItem(el, options);
      if (item.isImage) {
        if (!item.isBackgroundImage) {
          el.setAttribute('data-rimg-template-svg', el.getAttribute('srcset'));
        }
    
        loadImage(item);
      }
    }
    
    /**
     * Prepare an element to be displayed on the screen.
     *
     * Images have special logic applied to them to swap out the different sources.
     *
     * @fires rimg:enter
     *        The element is entering the viewport.
     *
     * @param {HTMLElement} el
     * @param {Settings} options
     */
    function update(el, options) {
      if (!el) return;
      trigger(el, 'rimg:update');
    
      var item = parseItem(el, options);
    
      if (item.isImage) {
        if (!item.isBackgroundImage) {
          el.setAttribute('data-rimg', 'lazy');
          el.setAttribute('srcset', el.getAttribute('data-rimg-template-svg'));
        }
    
        loadImage(item);
      }
    }
    
    /**
     * @typedef {Object} Size
     * @property {Number} width
     * @property {Number} height
     */
    
    /**
     * A function to turn a template string into a URL.
     *
     * @callback TemplateRenderer
     * @param {String} template
     * @param {Size} size
     * @returns {String}
     */
    
    /**
     * @typedef {Object} Settings
     *
     * @property {String} [template]
     *           A template string used to generate URLs for an image. This allows us to
     *           dynamically load images with sizes to match the container's size.
     *
     * @property {TemplateRenderer} [templateRender]
     *           A function to turn a template string into a URL.
     *
     * @property {Size} [max]
     *           The maximum available size for the image. This ensures we don't
     *           try to load an image larger than is possible.
     *
     * @property {Number} [round]
     *           Round image dimensions to the nearest multiple. This is intended to
     *           tax the image server less by lowering the number of possible image
     *           sizes requested.
     *
     * @property {Size} [placeholder]
     *           The size of the lo-fi image to load before the full image.
     */
    
    /**
     * Initialize the responsive image handler.
     *
     * @param {String|HTMLElement|NodeList} selector
     *        The CSS selector, element, or elements to track for lazy-loading.
     *
     * @param {Settings} options
     *
     * @returns {PublicApi}
     */
    function rimg() {
      var selector = arguments.length > 0 && arguments[0] !== undefined ? arguments[0] : '[data-rimg="lazy"]';
      var options = arguments.length > 1 && arguments[1] !== undefined ? arguments[1] : {};
    
      // Intersections
      var io = new IntersectionObserver(function (entries) {
        entries.forEach(function (entry) {
          if (entry.isIntersecting || entry.intersectionRatio > 0) {
            io.unobserve(entry.target);
            load(entry.target, options);
          }
        });
      }, {
        // Watch the viewport, with 20% vertical margins
        rootMargin: '20% 0px'
      });
    
      /**
       * @typedef {Object} PublicApi
       */
      var api = {
        /**
         * Track a new selector, element, or nodelist for lazy-loading.
         * @type Function
         * @param {String|HTMLElement|NodeList} selector
         */
        track: function track() {
          var selector = arguments.length > 0 && arguments[0] !== undefined ? arguments[0] : '[data-rimg="lazy"]';
    
          var els = querySelector(selector);
          for (var i = 0; i < els.length; i++) {
            io.observe(els[i]);
          }
        },
        update: function update$$1() {
          var selector = arguments.length > 0 && arguments[0] !== undefined ? arguments[0] : '[data-rimg="loaded"]';
    
          var els = querySelector(selector);
          for (var i = 0; i < els.length; i++) {
            update(els[i], options);
          }
        },
    
    
        /**
         * Stop tracking element(s) for lazy-loading.
         * @type Function
         * @param {String|HTMLElement|NodeList} selector
         */
        untrack: function untrack() {
          var selector = arguments.length > 0 && arguments[0] !== undefined ? arguments[0] : '[data-rimg]';
    
          var els = querySelector(selector);
          for (var i = 0; i < els.length; i++) {
            io.unobserve(els[i]);
          }
        },
    
    
        /**
         * Unload all event handlers and observers.
         * @type Function
         */
        unload: function unload() {
          io.disconnect();
        }
      };
    
      // Add initial elements
      api.track(selector);
    
      return api;
    }
    
    /**
     * Finds a group of elements on the page.
     *
     * @param {String|HTMLElement|NodeList} selector
     * @returns {Object} An array-like object.
     */
    function querySelector(selector) {
      if (typeof selector === 'string') {
        return document.querySelectorAll(selector);
      }
    
      if (selector instanceof HTMLElement) {
        return [selector];
      }
    
      if (selector instanceof NodeList) {
        return selector;
      }
    
      return [];
    }
    
    return rimg;
    
    })));
    
    /*!
     * rimg-shopify v2.2.0
     * (c) 2018 Pixel Union
     */
    (function (global, factory) {
    	typeof exports === 'object' && typeof module !== 'undefined' ? module.exports = factory(require('rimg')) :
    	typeof define === 'function' && define.amd ? define(['rimg'], factory) :
    	(global.rimg = global.rimg || {}, global.rimg.shopify = factory(global.rimg));
    }(this, (function (rimg) { 'use strict';
    
    rimg = rimg && rimg.hasOwnProperty('default') ? rimg['default'] : rimg;
    
    /**
     * Polyfill for Element.matches().
     *
     * @see https://developer.mozilla.org/en-US/docs/Web/API/Element/matches
     */
    if (!Element.prototype.matches) {
      Element.prototype.matches = Element.prototype.matchesSelector || Element.prototype.mozMatchesSelector || Element.prototype.msMatchesSelector || Element.prototype.oMatchesSelector || Element.prototype.webkitMatchesSelector || function (s) {
        var matches = (this.document || this.ownerDocument).querySelectorAll(s),
            i = matches.length;
        while (--i >= 0 && matches.item(i) !== this) {}
        return i > -1;
      };
    }
    
    var state = {
      init: init,
      watch: watch,
      unwatch: unwatch
    };
    
    function init() {
      var selector = arguments.length > 0 && arguments[0] !== undefined ? arguments[0] : '[data-rimg="lazy"]';
      var options = arguments.length > 1 && arguments[1] !== undefined ? arguments[1] : {};
    
      state.selector = selector;
      state.instance = rimg(selector, options);
      state.loadedWidth = Math.max(document.documentElement.clientWidth, window.innerWidth || 0);
    
      // Listen for Shopify theme editor events
      document.addEventListener('shopify:section:load', function (event) {
        return watch(event.target);
      });
    
      window.addEventListener('resize', function () {
        return _update();
      });
    
      document.addEventListener('shopify:section:unload', function (event) {
        return unwatch(event.target);
      });
    
      // Listen for custom events to allow themes to hook into rimg
      document.addEventListener('theme:rimg:watch', function (event) {
        return watch(event.target);
      });
    
      document.addEventListener('theme:rimg:unwatch', function (event) {
        return unwatch(event.target);
      });
    
      // Support custom events triggered through jQuery
      // See: https://github.com/jquery/jquery/issues/3347
      if (window.jQuery) {
        jQuery(document).on({
          'theme:rimg:watch': function themeRimgWatch(event) {
            return watch(event.target);
          },
          'theme:rimg:unwatch': function themeRimgUnwatch(event) {
            return unwatch(event.target);
          }
        });
      }
    }
    
    /**
     * Track an element, and its children.
     *
     * @param {HTMLElement} el
     */
    function watch(el) {
      // Track element
      if (typeof el.matches === 'function' && el.matches(state.selector)) {
        state.instance.track(el);
      }
    
      // Track element's children
      state.instance.track(el.querySelectorAll(state.selector));
    }
    
    /**
     * Untrack an element, and its children
     *
     * @param {HTMLElement} el
     * @private
     */
    function unwatch(el) {
      // Untrack element's children
      state.instance.untrack(el.querySelectorAll(state.selector));
    
      // Untrack element
      if (typeof el.matches === 'function' && el.matches(state.selector)) {
        state.instance.untrack(el);
      }
    }
    
    /**
     * Update an element, and its children.
     *
     * @param {HTMLElement} el
     */
    function _update() {
      var currentWidth = Math.max(document.documentElement.clientWidth, window.innerWidth || 0);
    
      // Return if we're not 2x smaller, or larger than the existing loading size
      if (currentWidth / state.loadedWidth > 0.5 && currentWidth / state.loadedWidth < 2) {
        return;
      }
    
      state.loadedWidth = currentWidth;
      state.instance.update();
    }
    
    return state;
    
    })));
    
;

window.ThemeView = (function(superClass) {
  extend(ThemeView, superClass);

  function ThemeView() {
    return ThemeView.__super__.constructor.apply(this, arguments);
  }

  ThemeView.prototype.el = document.body;

  ThemeView.prototype.initialize = function() {
    var body;
    body = $(document.body);
    this.isHome = body.hasClass('template-index');
    this.isCollection = body.hasClass('template-collection');
    this.isListCollections = body.hasClass('template-list-collections');
    this.isProduct = body.hasClass('template-product');
    this.isProductSlideshow = body.hasClass('template-product-slideshow');
    this.isCart = body.hasClass('template-cart');
    this.isContactPage = body.hasClass('template-page-contact');
    this.isFAQPage = body.hasClass('template-page-faq');
    this.isGiftCardPage = body.hasClass("gift-card-template");
    this.isBlog = body.hasClass('template-blog') || body.hasClass('template-article');
    this.isAccount = body.attr('class').indexOf('-customers-') > 0;
    return this.is404 = body.hasClass('template-404');
  };

  ThemeView.prototype.render = function() {
    this.sections = new ThemeEditor();
    this.sections.register('header', this.headerSetup(this.sections));
    this.sections.register('pxs-map', this.mapSetup(this.sections));
    rimg.shopify.init();
    this.slideshowSection = new SlideshowSection({
      el: this.$el
    });
    if (this.isHome) {
      this.homeView = new HomeView({
        el: this.$el
      });
      this.homeView.render();
    }
    if (this.isCollection) {
      this.collectionView = new CollectionView({
        el: this.$el
      });
      this.collectionView.render();
    }
    if (this.isListCollections) {
      this.listCollectionsView = new ListCollectionsView({
        el: $('.collections-list')
      });
      this.listCollectionsView.render();
    }
    if (this.isGiftCardPage) {
      this.giftcardView = new GiftCardView({
        el: this.$el
      });
    }
    if (this.isContactPage) {
      new ContactView({
        el: this.$el
      });
    }
    if (this.isFAQPage) {
      new AccordionView({
        el: this.$el
      });
    }
    if (this.isProduct || this.isProductSlideshow) {
      new ProductView({
        el: this.$el,
        bindSection: true
      });
    }
    if (this.isCart) {
      new CartView({
        el: this.$el
      });
    }
    if (this.isBlog) {
      new BlogView({
        el: this.$el
      });
    }
    if (this.isAccount) {
      this.accountView = new AccountView({
        el: this.$el
      });
      this.accountView.render();
    }
    if (this.is404) {
      this.notFoundView = new NotFoundView({
        el: this.$el
      });
      this.notFoundView.render();
    }
    if (Theme.currencySwitcher) {
      this.currencyView = new CurrencyView({
        el: this.$el
      });
    }
    if ($('html').hasClass('lt-ie10')) {
      this.inputPlaceholderFix();
    }
    this.rteViews = [];
    this.richTextInit();
    window.ThemeUtils.externalLinks(this.$el);
    $(document).on('shopify:section:load', (function(_this) {
      return function(event) {
        window.ThemeUtils.externalLinks($(event.target));
        return _this.richTextInit();
      };
    })(this));
    return $(document).on('shopify:section:unload', (function(_this) {
      return function() {
        var j, len, ref, results, rte;
        ref = _this.rteViews;
        results = [];
        for (j = 0, len = ref.length; j < len; j++) {
          rte = ref[j];
          results.push(rte.undelegateEvents());
        }
        return results;
      };
    })(this));
  };

  ThemeView.prototype.richTextInit = function() {
    var j, len, ref, results, rte;
    ref = $('.rte');
    results = [];
    for (j = 0, len = ref.length; j < len; j++) {
      rte = ref[j];
      results.push(this.rteViews.push(new RTEView({
        el: rte
      })));
    }
    return results;
  };

  ThemeView.prototype.inputPlaceholderFix = function() {
    var input, j, len, placeholders, text;
    placeholders = $('[placeholder]');
    for (j = 0, len = placeholders.length; j < len; j++) {
      input = placeholders[j];
      input = $(input);
      if (!(input.val().length > 0)) {
        text = input.attr('placeholder');
        input.attr('value', text);
        input.data('original-text', text);
      }
    }
    placeholders.focus(function() {
      input = $(this);
      if (input.val() === input.data('original-text')) {
        return input.val('');
      }
    });
    return placeholders.blur(function() {
      input = $(this);
      if (input.val().length === 0) {
        return input.val(input.data('original-text'));
      }
    });
  };

  ThemeView.prototype.headerSetup = function(sections) {
    return {
      instances: {},
      init: function(instance) {
        return this.instances[instance.sectionId] = new HeaderView();
      },
      onSectionLoad: function(event) {
        var instance;
        instance = sections.getInstance(event);
        if (!this.instances[instance.sectionId]) {
          return this.init(instance);
        }
      },
      onSectionUnload: function(event) {
        var instance, ref;
        instance = sections.getInstance(event);
        if ((ref = this.instances[instance.sectionId]) != null) {
          ref.unBindEvents();
        }
        return delete this.instances[instance.sectionId];
      }
    };
  };

  ThemeView.prototype.mapSetup = function(sections) {
    return {
      instances: {},
      init: function(instance) {
        return this.instances[instance.sectionId] = new PxsMap({
          el: instance.el,
          data: instance.data
        });
      },
      onSectionLoad: function(event) {
        var instance;
        instance = sections.getInstance(event);
        if (!this.instances[instance.sectionId]) {
          return this.init(instance);
        }
      },
      onSectionUnload: function(event) {
        var instance;
        instance = sections.getInstance(event);
        this.instances[instance.sectionId].onSectionUnload();
        return delete this.instances[instance.sectionId];
      }
    };
  };

  return ThemeView;

})(Backbone.View);

$(function() {
  window.theme = new ThemeView();
  return theme.render();
});
